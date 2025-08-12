# Docker Build & Push Workflow

This workflow builds a Docker image for your Java project and pushes it to Docker Hub.

## Triggers

- As a reusable workflow (`workflow_call`)

## Inputs

- `project_name`: Name of the project (used for image tagging).

## Secrets Required

- `DOCKERHUB_USERNAME`
- `DOCKERHUB_PASSWORD`

## Jobs

- **docker**:
  - Checks out code.
  - Downloads Maven build artifacts.
  - Builds and tags Docker images.
  - Pushes images to Docker Hub.

---
