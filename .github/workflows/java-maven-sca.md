# Dependency Scanning (SCA) Workflow

This workflow performs Software Composition Analysis (SCA) to detect vulnerabilities in dependencies and application images.

## Triggers

- Manual (`workflow_dispatch`)
- As a reusable workflow (`workflow_call`)

## Inputs

- `project_name` (optional): Name of the project.

## Secrets Required

- `DOCKERHUB_USERNAME`
- `DOCKERHUB_PASSWORD`
- `SNYK_TOKEN`

## Jobs

- **sca**:
  - Checks out code.
  - Sets up Java.
  - Runs Snyk-based dependency scan.
- **vulnerability-scan**:
  - Calls the reusable vulnerability scan workflow
