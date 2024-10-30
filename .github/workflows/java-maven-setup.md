# Setup Job

## Overview
The `setup` job is responsible for preparing the environment for the subsequent jobs. It checks out the code from the repository, sets up the correct version of Java (Zulu distribution), and caches Maven dependencies to speed up the build process.

## Key Steps
1. **Check out code**: Uses the `actions/checkout@v4` action to pull the latest code from the repository.
2. **Set up Java**: Configures the environment to use Java 17 (Zulu distribution).
3. **Cache Maven dependencies**: Caches the `.m2` Maven repository to avoid downloading dependencies repeatedly across jobs.

## Outputs
- **cache-key**: A unique key for the Maven cache, used to restore dependencies in future jobs.
