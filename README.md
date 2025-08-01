# JWK Generator Widget

A web-based tool for converting between PEM-formatted keys and JSON Web Keys (JWK) format. This widget provides three main functionalities:

- **PEM to JWK**: Convert PEM-encoded keys and certificates to JWK format
- **JWK to PEM**: Convert JWK format back to PEM encoding
- **Generate New Key**: Create new cryptographic keys in various formats

## Features

- **PEM to JWK Conversion**: Convert PEM-encoded keys and certificates to JWK format
- **Key Fingerprint Generation**: Generate SHA-256 fingerprints for keys
- **Multiple Key Types**: Support for RSA, ECDSA, EdDSA, and X25519 keys
- **Customizable Metadata**: Add key ID, algorithm, usage, and operations
- **Syntax Highlighting**: JSON output with syntax highlighting

## Quick Start

1. **Install dependencies**:
   ```bash
   npm install
   ```

2. **Start development server**:
   ```bash
   npm run dev
   ```

3. **Build for production**:
   ```bash
   npm run build
   ```

## Usage

1. Open the application in your browser
2. Select "PEM to JWK" tab
3. Paste your PEM-encoded key or certificate
4. Optionally configure:
   - Key ID (kid)
   - Algorithm (alg)
   - Key usage (use)
   - Key operations (key_ops)
5. Click "Generate JWK" to convert

## Supported Formats

- **PEM Encoded Keys**: Traditional Privacy-Enhanced Mail format
  - Public keys (RSA, EC, Ed25519, Ed448, X25519, X448)
  - Private keys (RSA, EC, Ed25519, Ed448, X25519, X448)
  - Encrypted private keys (PKCS#8 with password protection)
- **X.509 Certificates**: Digital certificates in PEM format
- **JSON Web Keys (JWK)**: RFC 7517 compliant key format
  - Individual keys
  - JWK Sets (multiple keys)
- **Key Generation**: Create new keys in various formats and sizes

## Supported Key Types

- **RSA**: Digital signatures and encryption (RS256, RS384, RS512, PS256, PS384, PS512)
- **ECDSA**: Digital signatures with elliptic curves (ES256, ES384, ES512)
- **Ed25519**: Modern digital signatures using EdDSA algorithm
- **Ed448**: High-security digital signatures using EdDSA algorithm
- **X25519**: Key exchange and encryption using Curve25519
- **X448**: High-security key exchange using Curve448

## Technologies

- React 18
- TypeScript
- Vite
- jose (JWT/WebCrypto library)
- Prism.js (syntax highlighting)

## Development

```bash
npm run type-check  # Type checking
npm run preview     # Preview production build
```

## Deployment

This project is automatically deployed to GitHub Pages using GitHub Actions. The deployment workflow:

- Triggers on pushes to the `main` branch and pull requests
- Builds the project using `npm run build`
- Deploys to GitHub Pages using the `actions/deploy-pages` action
- Uses a single job for building and deploying (no artifacts between jobs)

The workflow file is located at `.github/workflows/deploy.yml`.

### Manual Deployment

To deploy manually:

1. Build the project: `npm run build`
2. The built files will be in the `dist/` directory
3. Deploy the contents of `dist/` to your web server 