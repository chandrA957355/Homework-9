# Homework 9: QR Code API with CI/CD Pipeline

This project implements a QR Code generation API using FastAPI, paired with a CI/CD pipeline that ensures high code quality and security. The API allows authenticated users to generate, list, and delete QR codes.

## Features

- **QR Code Management:** 
  - Create, list, and delete QR codes.
  - Secure operations with OAuth2 authentication.
- **CI/CD Pipeline:** 
  - Automated testing, Docker image builds, and vulnerability scans.
  - Integrated with GitHub Actions for seamless deployment.

## Fixes and Improvements

During development, several issues were resolved to ensure a stable and functional pipeline:

1. **Authentication Issues in Tests:**
   - Resolved a `401 Unauthorized` error by ensuring correct handling of OAuth2 tokens.
   
2. **Duplicate QR Code Creation:**
   - Fixed handling of existing QR codes by returning a `409 Conflict` status, ensuring proper idempotency.

3. **Docker Image Tagging and Pushing:**
   - Corrected Docker image tagging to include the `docker.io` prefix for compatibility with Docker Hub.

4. **Vulnerability Scanning Failures:**
   - Addressed Trivy scanning errors by setting up `TRIVY_GITHUB_TOKEN` to handle rate limits and avoid `TOOMANYREQUESTS` errors.

5. **Dependency Vulnerabilities:**
   - Upgraded `gunicorn` to `22.0.0` to fix CVE-2024-1135.
   - Maintained FastAPI compatibility by locking `starlette` to `0.40.0`.

### Prerequisites

- Python 3.10 or higher
- Docker installed and running
- Trivy for local vulnerability scanning

