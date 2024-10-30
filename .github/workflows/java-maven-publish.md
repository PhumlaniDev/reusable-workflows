# Publish Job

## Overview
The `publish_nexus` job is responsible for publishing Maven artifacts to GitHub Packages and other Nexus repositories (if configured). It runs after the vulnerability scan to ensure only secure artifacts are deployed.

## Key Steps
1. **Check out code**: Pulls the latest code from the repository.
2. **Restore Maven cache**: Ensures that Maven dependencies are restored from the cache.
3. **Deploy Artifacts**: Uses `mvn deploy` to upload the built artifacts to the configured Maven repository.

## Requirements
- GitHub PAT and username must be provided in the repository secrets.
- Nexus repository should be configured in the `settings.xml` file.
