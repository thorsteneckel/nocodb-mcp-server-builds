# NocoDB MCP Server - Docker Builds

This repository contains the CI/CD pipeline for building and publishing Docker images of the [NocoDB MCP Server](https://github.com/edwinbernadus/nocodb-mcp-server).

## Overview

This repository automatically builds Docker images from the source repository `edwinbernadus/nocodb-mcp-server` and publishes them to the GitHub Container Registry (ghcr.io).

## Docker Images

Docker images are automatically built and pushed to GitHub Container Registry on every push to the `main` branch.

### Image Location

```
ghcr.io/<your-username>/nocodb-mcp-server
```

### Image Tags

- `latest` - Latest build from main branch
- `sha-<short-sha>` - Tagged with Git commit SHA for specific versions

## Usage

### Pull the Docker Image

```bash
docker pull ghcr.io/<your-username>/nocodb-mcp-server:latest
```

### Run the Container

```bash
docker run -e NOCODB_URL=https://your-nocodb-instance.com \
           -e NOCODB_API_TOKEN=your_api_token \
           -e NOCODB_BASE_ID=your_base_id \
           ghcr.io/<your-username>/nocodb-mcp-server:latest
```

## Source Repository

The Docker images are built from: [edwinbernadus/nocodb-mcp-server](https://github.com/edwinbernadus/nocodb-mcp-server)

## GitHub Actions

The build process is automated using GitHub Actions. The workflow:
1. Checks out the source repository
2. Builds the Docker image using Docker Buildx
3. Tags the image with `latest` and Git SHA
4. Pushes to GitHub Container Registry

## License

This repository follows the same license as the source repository (MIT).

