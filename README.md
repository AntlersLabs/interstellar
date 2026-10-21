# Patched PHP 8.4.27 Base Image (`php:8.4-fpm-alpine`)

Emergency security base image containing the official fix for:
- **CVE-2026-109618** & **CVE-2026-109619** ("PHP2Shell" unauthenticated RCE)
- Upstream base: Alpine 3.24, PHP-FPM 8.4.27

## Published Images
- `ghcr.io/exeis-ixt/php:8.4-fpm-alpine`
- `ghcr.io/exeis-ixt/php:8.4.27-fpm-alpine`

## Usage in Laravel / App Dockerfile
Replace the upstream unpatched image reference:
```dockerfile
FROM ghcr.io/exeis-ixt/php:8.4-fpm-alpine
```

## Pull & Deploy on Podman / Production
```bash
podman pull ghcr.io/exeis-ixt/php:8.4-fpm-alpine
podman compose build --no-cache app
podman compose up -d app
podman compose exec app php -v
```
