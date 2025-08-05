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
```