# JWT Decoder

A simple, secure, and privacy-focused JWT (JSON Web Token) decoder that runs entirely in your browser. No server-side processing, no data transmission - your tokens stay on your device.

🔗 **Live Demo**: [https://jwt.kartavets.com/](https://jwt.kartavets.com/)

## Features

- 🔒 **100% Client-Side**: All decoding happens in your browser
- 🎨 **Syntax Highlighting**: Beautiful JSON output with Prism.js
- 🌓 **Dark/Light Theme**: Auto-detects system preference with manual override
- 📱 **Responsive Design**: Works seamlessly on desktop and mobile
- 📋 **One-Click Copy**: Easy clipboard access for decoded tokens
- 🚀 **Example Library**: Pre-loaded JWT examples (Access Token, ID Token, Refresh Token)
- ♿ **Accessible**: Full keyboard navigation and screen reader support
- ⚡ **Fast & Lightweight**: Single HTML file, minimal dependencies

## Technology Stack

- **Frontend**: Vanilla JavaScript, HTML5, CSS3
- **JWT Library**: [jose](https://github.com/panva/jose) v6.0.11
- **Syntax Highlighting**: [Prism.js](https://github.com/PrismJS/prism)
- **Deployment**: AWS S3 + CloudFront
- **CI/CD**: GitHub Actions

## Quick Start

### Local Development

1. Clone the repository:
```bash
git clone https://github.com/vlade11115/k_jwt.git
cd k_jwt
```

2. Open the application:
```bash
# Option 1: Direct browser opening
open src/index.html

# Option 2: Using Python's built-in server
python3 -m http.server 8000
# Navigate to http://localhost:8000/src/
```

That's it! No build process or dependencies to install.

## Usage

1. **Paste a JWT**: Copy any JWT token and paste it into the text area
2. **Decode**: Click "Decode Token" or press `Ctrl/Cmd + Enter`
3. **View Results**: See the decoded header and payload with syntax highlighting
4. **Copy Output**: Click "Copy JSON" to copy the decoded result

### Example Tokens

The application includes three pre-configured examples:

- **Access Token**: OAuth 2.0 token with scopes and permissions
- **ID Token**: OpenID Connect token with user identity claims
- **Refresh Token**: Long-lived token for obtaining new access tokens

## Security & Privacy

- ✅ No server-side processing
- ✅ No analytics or tracking
- ✅ No external requests (except CDN libraries)
- ✅ No data storage or cookies (except theme preference)
- ✅ Open source and auditable

## Deployment

The site is automatically deployed to AWS S3/CloudFront when changes are pushed to the `main` branch. See [DEPLOYMENT.md](DEPLOYMENT.md) for detailed deployment instructions.

### Required GitHub Secrets

- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION`
- `S3_BUCKET_NAME`
- `CLOUDFRONT_DISTRIBUTION_ID`

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

### Development Guidelines

1. Keep it simple - single HTML file approach
2. No build process or transpilation
3. Maintain accessibility standards
4. Test on multiple browsers and devices
5. Follow existing code style

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Vladyslav Kartavets**

- GitHub: [@vlade11115](https://github.com/vlade11115)
- Website: [https://jwt.kartavets.com/](https://jwt.kartavets.com/)

## Acknowledgments

- [jose](https://github.com/panva/jose) - JWT library
- [Prism.js](https://github.com/PrismJS/prism) - Syntax highlighting
- [jwt.io](https://jwt.io) - Inspiration for the project

---

Made with ❤️ for the developer community