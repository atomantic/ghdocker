# GitHub Docker Publication Integrity Test

This repository demonstrates a test scenario for GitHub Docker publication integrity.

## Purpose

This repo contains a simple shell application that prints "hello world". It includes a GitHub Actions workflow that automatically builds and publishes Docker images to GitHub Container Registry when commits are pushed to main.

## Test Scenario

The test demonstrates a potential security concern where the published Docker image may not match the code in the repository.

## Docker Image

The application is containerized and published to:
```
ghcr.io/atomantic/ghdocker:latest
```

## Running the Application

```bash
docker run ghcr.io/atomantic/ghdocker:latest
Unable to find image 'ghcr.io/atomantic/ghdocker:latest' locally
latest: Pulling from atomantic/ghdocker
4f4fb700ef54: Pull complete
b6dc7043acb2: Pull complete
Digest: sha256:b367a9b02c15f652a8145c416cb0c1de8238fc7d6c989858a3727cde3d5a8962
Status: Downloaded newer image for ghcr.io/atomantic/ghdocker:latest
hello hidden code
```

Notice that the sha hash does not match the hash built in github actions and pushed as latest/main, but we have overwritten the main/latest tags manually with a modified code that has not been committed to the repo.
