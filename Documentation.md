# `requirements.txt` Documentation

## What is `requirements.txt`?

The `requirements.txt` file is a standard Python convention used to **list project dependencies**. It defines all the external libraries (packages) that your Python project needs to run successfully.

---

## Why is `requirements.txt` Important?

-  Ensures **consistent environment setup** across different machines and deployments.
-  Helps automate installation of dependencies using a simple command (`pip install -r requirements.txt`).
-  Essential for **collaboration**, CI/CD pipelines, and production readiness.
-  Supports reproducibility in **Docker**, **virtual environments**, and **cloud deployments**.

---

## Use Cases

| Scenario                         | How `requirements.txt` Helps                                      |
|----------------------------------|--------------------------------------------------------------------|
|  Team Development              | Everyone installs the same versions, preventing "it works on my machine" issues |
|  Deployment to Servers         | Easily install all dependencies in production                     |
|  Setting up CI/CD              | Automate dependency installation before testing/build             |
|  Docker Image Creation         | Add to Dockerfiles to streamline image build                      |
|  Virtual Environments          | Pairs perfectly with `venv` or `virtualenv`                       |

---

## Versioning Best Practices

Version control is **crucial** to avoid conflicts and bugs when dependencies change over time.

| Syntax               | Meaning                                      | Example                      |
|----------------------|----------------------------------------------|------------------------------|
| `package`            | Latest version (not recommended)             | `requests`                  |
| `package==1.2.3`     | Exact version (most stable for prod)         | `flask==2.2.3`              |
| `package>=1.2.0`     | Minimum version allowed                      | `pandas>=1.4.0`             |
| `package<=2.0.0`     | Maximum version allowed                      | `tensorflow<=2.14.0`        |
| `package~=1.4.5`     | Compatible release (same major/minor)        | `numpy~=1.24.1`             |
| `# comment`          | Comments are allowed                         | `# Core HTTP library`       |

---

## Best Practices

-  **Pin exact versions** (`==`) for production deployments.
-  Use **compatible versions** (`~=` or `>=`) during development.
-  Add **comments** next to packages for clarity.
-  Avoid mixing system-level packages with project-specific ones.
-  Regularly test and update dependencies to avoid vulnerabilities.
-  Generate using `pip freeze > requirements.txt` for complete snapshots.

---

### How to Use

```bash
# Install all dependencies from requirements.txt
pip install -r requirements.txt
