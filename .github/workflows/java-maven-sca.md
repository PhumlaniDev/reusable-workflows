# Dependency & Vulnerability Scanning Workflow

This GitHub Actions workflow performs two key security checks:

1. **Dependency Scanning (SCA)** – Scans Maven project dependencies for known vulnerabilities using **Snyk**.
2. **Container Vulnerability Scan** – Scans the built Docker image for OS and library vulnerabilities using **Trivy**.

---

## 📌 Triggers

This workflow can be:

- **Manually triggered** via `workflow_dispatch`.
- **Reused** in other workflows via `workflow_call`.

---

## 🔧 Inputs

When called as a reusable workflow, the following inputs must be provided:

| Input       | Description                   | Required | Type   |
| ----------- | ----------------------------- | -------- | ------ |
| `image_tag` | Full Docker image tag to scan | ✅       | string |

---

## 🔑 Secrets

| Secret       | Description                                       | Required |
| ------------ | ------------------------------------------------- | -------- |
| `SNYK_TOKEN` | API token for Snyk to perform dependency scanning | ✅       |

---

## 🛠 Jobs

### 1. `sca`

- **Purpose:** Scans Maven project dependencies using **Snyk**.
- **Steps:**
  - Checks out code.
  - Sets up Java 21 with Maven cache.
  - Forces DNS resolution for reliability.
  - Runs Snyk dependency analysis and outputs results as `crda-report.json`.

### 2. `vulnerability_scan`

- **Purpose:** Scans the provided Docker image for vulnerabilities using **Trivy**.
- **Steps:**
  - Checks out code.
  - Downloads and loads a previously built Docker image from artifacts.
  - Runs Trivy with **SARIF** output.
  - Uploads the results to the **GitHub Security tab**.

---

## 📤 Outputs

- `crda-report.json` – Snyk dependency scan results.
- `trivy-results.sarif` – Container vulnerability scan report viewable in GitHub Security.

---

## 🔗 Example Usage in a Main Workflow

```yaml
jobs:
  security_scans:
    uses: ./.github/workflows/dependency-scanning.yml
    with:
      image_tag: my-docker-org/my-service:latest
    secrets:
      SNYK_TOKEN: ${{ secrets.SNYK_TOKEN }}
```
