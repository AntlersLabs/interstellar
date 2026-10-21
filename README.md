# Patched PHP 8.4.27 Base Image (`php:8.4-fpm-alpine`)

AntlersLabs emergency security base image containing the official fix for:
- **CVE-2026-109618** & **CVE-2026-109619** ("PHP2Shell" unauthenticated RCE)
- Upstream base: Alpine 3.24, PHP-FPM 8.4.27

## Published Images
- `ghcr.io/antlerslabs/php:8.4-fpm-alpine`
- `ghcr.io/antlerslabs/php:8.4.27-fpm-alpine`
- `ghcr.io/antlerslabs/php:latest-fpm-alpine`

## Usage in App / Laravel Dockerfile (`kpr_quotation`)
Replace the upstream unpatched image reference:
```dockerfile
FROM ghcr.io/antlerslabs/php:8.4-fpm-alpine
```

## Pull & Deploy on Podman / Production Server
```bash
# Pull the patched base image from AntlersLabs GHCR
podman pull ghcr.io/antlerslabs/php:8.4-fpm-alpine

# Rebuild your application image without cache
podman compose build --no-cache app

# Recreate and start the container
podman compose up -d app

# Verify the container is running the patched 8.4.27 binary
podman compose exec app php -v
```
