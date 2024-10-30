# Lint Job

## Overview

The `lint` job is responsible for checking the code style and formatting using `Checkstyle`. It ensures that the code follows predefined style guidelines before it is built or tested.

## Key Steps

1. **Check out code**: Uses the `actions/checkout@v4` action to pull the latest code from the repository.
2. **Set up Java**: Configures the environment to use Java 17 (Zulu distribution).
3. **Run Lint**: Executes the `mvn checkstyle:check` command to check for any code style violations.

## Requirements

- Maven should have a `checkstyle` plugin configured in the `pom.xml` file.
