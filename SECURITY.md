# Security policy

## Principles
- Secrets stay in environment variables only.
- All tokens are validated and checked for issuer, audience, expiration, and signature.
- User-facing interfaces must escape untrusted text and never access the database directly.
- Uploaded files are validated, constrained, and processed with safe defaults.

## Reporting vulnerabilities
Please report security issues privately to the project maintainers and avoid creating public issues for sensitive vulnerabilities.
