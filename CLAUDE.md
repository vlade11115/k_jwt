# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a JWT Token Decoder web application - a standalone, client-side HTML application that decodes JSON Web Tokens without requiring any backend infrastructure.

## Architecture

The entire application is contained in a single `src/index.html` file that includes:
- HTML structure for the UI
- Inline CSS styling
- JavaScript code that uses the jose library (v6.0.11) loaded from CDN
- ES6 module import for the jose library

## Key Components

### JWT Decoding Logic
- Uses `jose.decodeJwt()` for payload extraction
- Uses `jose.decodeProtectedHeader()` for header extraction
- Combines both into a single JSON output structure

### External Dependencies
- jose library v6.0.11: `https://unpkg.com/jose@6.0.11/dist/webapi/index.js`
- Loaded as ES6 module and exposed to global scope via `window.jose`

## Development Commands

No build process required. To run the application:
```bash
# Open directly in browser
open src/index.html

# Or use a simple HTTP server
python3 -m http.server 8000
# Then navigate to http://localhost:8000
```

## Testing

To test the application, use sample JWT tokens such as:
```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
```

## Important Notes

- The application performs client-side decoding only (no signature verification)
- All processing happens in the browser - no data is sent to any server
- The jose library is loaded from unpkg CDN - internet connection required