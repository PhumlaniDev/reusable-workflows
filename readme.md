# Reusable Workflows Repository

## Overview

This repository contains a collection of reusable GitHub Actions workflows designed to streamline CI/CD processes across multiple projects. By encapsulating common tasks into reusable workflows, you can reduce duplication, improve consistency, and simplify your CI/CD pipeline management.

## Available Workflows

The following workflows are available for use:

1. **Setup Workflow**

   - Sets up the environment for the project, including dependencies and configurations.

2. **Lint Code Workflow**

   - Automates code linting to ensure adherence to coding standards and styles.

3. **Build, Test, and Analyze Workflow**

   - Handles the build process, runs tests, and performs code analysis using SonarQube.

4. **Vulnerability Scan Workflow**

   - Scans for vulnerabilities in dependencies and application code.

5. **Publish Workflow**
   - Publishes built artifacts to a specified repository, such as Nexus or GitHub Packages.

## Usage

To use these workflows in your own repository, you can reference them in your own workflow files. Below is an example of how to call a reusable workflow:

```yaml
name: CI Pipeline

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  setup:
    uses: <your-username>/<your-repo-name>/.github/workflows/setup.yml@main

  lint:
    uses: <your-username>/<your-repo-name>/.github/workflows/lint.yml@main

  build:
    uses: <your-username>/<your-repo-name>/.github/workflows/build-test-analyze.yml@main

  vulnerability-scan:
    uses: <your-username>/<your-repo-name>/.github/workflows/vulnerability-scan.yml@main

  publish:
    uses: <your-username>/<your-repo-name>/.github/workflows/publish.yml@main
```
