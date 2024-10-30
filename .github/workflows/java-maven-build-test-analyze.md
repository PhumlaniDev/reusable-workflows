# Build, Test, and Code Analysis (SonarQube) Job

## Overview
This job performs the following tasks:
- Builds the project using Maven.
- Runs unit tests.
- Analyzes the code with SonarQube.

It also integrates with PostgreSQL to run the application with a real database during the build process.

## Key Steps
1. **Check out code**: Pulls the latest code from the repository.
2. **Set up Java**: Configures the environment to use Java 17.
3. **Build with Maven**: Runs the `mvn clean install` command to compile the project and package the application.
4. **Run Unit Tests**: Executes `mvn test` to run the unit tests.
5. **SonarQube Analysis**: Uses the SonarQube Maven plugin to run static code analysis on the project.

## Services
- **PostgreSQL**: A PostgreSQL container is set up for database integration.

## Requirements
- SonarQube project key and token must be provided in the repository secrets.
