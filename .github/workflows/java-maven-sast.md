# Static Code Analysis (SAST) Workflow

This workflow performs static application security testing (SAST) for Java projects using multiple tools:

- **CodeQL**: Deep code analysis for security vulnerabilities.
- **SonarQube**: Static code analysis for code quality and security.
- **SpotBugs**: Bug detection for Java.
- **Semgrep**: Fast, open-source static analysis.

## Triggers

- Manual (`workflow_dispatch`)
- As a reusable workflow (`workflow_call`)

## Secrets Required

- `SONAR_TOKEN`
- `SONAR_URL`
- `SONAR_PROJECT_KEY`
- `SONAR_ORGANIZATION`

## Jobs

- **codeql**: Runs CodeQL analysis.
- **sonar**: Runs SonarQube analysis.
- **spotbugs**: Runs SpotBugs.
- **semgrep**: Runs Semgrep with security rules.

---
