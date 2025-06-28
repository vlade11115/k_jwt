# Deployment Guide

This project uses GitHub Actions for automated deployment to AWS S3 and CloudFront.

## How it works

The deployment is triggered when:
- Code is pushed directly to the `main` branch
- A pull request is merged into the `main` branch

## Required GitHub Secrets

You need to configure the following secrets in your GitHub repository settings (`Settings > Secrets and variables > Actions`):

### AWS Credentials
- `AWS_ACCESS_KEY_ID`: Your AWS access key ID
- `AWS_SECRET_ACCESS_KEY`: Your AWS secret access key
- `AWS_REGION`: AWS region where your resources are located (e.g., `us-east-1`)

### AWS Resources
- `S3_BUCKET_NAME`: Name of your S3 bucket (without s3:// prefix)
- `CLOUDFRONT_DISTRIBUTION_ID`: Your CloudFront distribution ID

## AWS IAM Permissions

The AWS user/role needs the following permissions:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket",
                "s3:GetObject",
                "s3:PutObject",
                "s3:DeleteObject"
            ],
            "Resource": [
                "arn:aws:s3:::your-bucket-name",
                "arn:aws:s3:::your-bucket-name/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "cloudfront:CreateInvalidation"
            ],
            "Resource": "arn:aws:cloudfront::*:distribution/your-distribution-id"
        }
    ]
}
```

## Deployment Process

1. **File Sync**: All files from the `src/` directory are synced to your S3 bucket
2. **Cache Control**: 
   - Static assets (JS, CSS, images): 1 year cache (`max-age=31536000`)
   - HTML, XML, TXT files: 5 minutes cache (`max-age=300`)
3. **CloudFront Invalidation**: All paths (`/*`) are invalidated to ensure fresh content delivery

## Site URL

After deployment, your site will be available at: https://jwt.kartavets.com/

## Troubleshooting

- Check the Actions tab in your GitHub repository for deployment logs
- Ensure all required secrets are configured correctly
- Verify AWS permissions are properly set
- Check S3 bucket policies and CloudFront settings if deployment succeeds but site doesn't update