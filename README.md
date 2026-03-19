# homeassistant-proxy

Nightly GitHub Actions workflow that pulls `homeassistant/home-assistant:latest`, recompresses it using **gzip** (instead of zstd), and pushes it to Docker Hub as `benhdavis/home-assistant:latest`.

Use this on NAS devices where Docker does not support zstd-compressed images.

## Setup

1. Go to **Settings → Secrets and variables → Actions** in this repo
2. Add two secrets:
   - `DOCKERHUB_USERNAME` — your Docker Hub username (`benhdavis`)
   - `DOCKERHUB_TOKEN` — a Docker Hub [access token](https://hub.docker.com/settings/security)

## Usage

On your NAS:

```yaml
image: benhdavis/home-assistant:latest
```

The image is rebuilt nightly. You can also trigger it manually from the **Actions** tab.
