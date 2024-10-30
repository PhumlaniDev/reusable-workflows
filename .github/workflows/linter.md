# Lint Code Workflow

## Overview
The **Lint Code** workflow automates code linting in your GitHub repository. It runs on every push, pull request, or when manually triggered, ensuring that code adheres to predefined style and formatting rules.

## Triggers
This workflow is triggered by:
- **Push Events**: When code is pushed to the repository.
- **Pull Request Events**: When a pull request is created or updated.
- **Manual Trigger**: When the workflow is dispatched manually.

## Job: Lint Code

### Steps
1. **Checkout Code**
   - Uses the `actions/checkout@v4` action to check out the repository code.
   - Sets `fetch-depth` to `0` to ensure all history is available for the linter.

2. **Lint Code**
   - Uses the `super-linter/super-linter@v7` GitHub Action to lint the code.
   - Configured to:
     - Automatically fix shell script formatting issues using `shfmt`.
     - Automatically format YAML files using `prettier`.

3. **Commit and Push Linting Fixes**
   - If the workflow is triggered by a pull request and the branch is not the default branch:
     - Uses `stefanzweifel/git-auto-commit-action@v5` to commit and push any fixes made by the linter.
     - The commit message is set to `"chore: fix linting issues"` and uses a predefined user for the commit.

### Permissions
- **Contents**: Read access to repository contents.
- **Statuses**: Write access to commit statuses.

## Requirements
- Ensure the repository has the required GitHub secrets configured, including `GITHUB_TOKEN`, to allow the linter to make commits and access the repository.

## Conclusion
This workflow helps maintain code quality by enforcing linting rules and automatically fixing issues, streamlining the code review process and improving collaboration.
