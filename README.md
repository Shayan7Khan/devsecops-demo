# devsecops-demo

## 1. Project Overview

**devsecops-demo** is a sample project showcasing DevSecOps best practices using a simple Flask application. It demonstrates secure application development, containerization, automated testing, security scanning, and CI/CD pipelines.

---

## 2. Features

- Flask web application served with Gunicorn
- Containerization with Docker
- Security scanning using [Trivy](https://github.com/aquasecurity/trivy)
- Automated CI/CD pipeline with GitHub Actions
- Unit testing with pytest
- Example workflow: fail on first push, fix, and pass

---

## 3. Prerequisites

- [Python 3.8+](https://www.python.org/downloads/)
- [Docker](https://www.docker.com/get-started)
- [Git](https://git-scm.com/)
- [Trivy](https://aquasecurity.github.io/trivy/v0.18.3/getting-started/installation/)
- [pytest](https://docs.pytest.org/en/stable/)
- GitHub account (for Actions)

---

## 4. Installation & Setup

### Local Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/devsecops-demo.git
   cd devsecops-demo
   ```

2. **Create a virtual environment and install dependencies:**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

3. **Run the Flask app locally:**
   ```bash
   flask run
   ```

### Docker Setup

1. **Build the Docker image:**
   ```bash
   docker build -t devsecops-demo .
   ```

2. **Run the container with Gunicorn:**
   ```bash
   docker run -p 8000:8000 devsecops-demo
   ```

---

## 5. Running Tests

Run unit tests using pytest:

```bash
pytest
```

Or, inside Docker:

```bash
docker run devsecops-demo pytest
```

---

## 6. Using Trivy for Scanning

Scan your Docker image for vulnerabilities:

```bash
trivy image devsecops-demo
```

Scan your source code for misconfigurations and secrets:

```bash
trivy fs .
```

---

## 7. GitHub Actions Workflow Explanation

This project includes a GitHub Actions workflow (`.github/workflows/ci.yml`) that:

- Installs dependencies
- Runs unit tests with pytest
- Builds the Docker image
- Runs Trivy scans for vulnerabilities
- Fails the build if tests or scans fail

---

## 8. How to Demonstrate (Fail -> Fix -> Pass)

1. **Fail:**  
   - Push a commit with a failing test or a known vulnerability (e.g., add a vulnerable package).
   - Observe the GitHub Actions workflow fail.

2. **Fix:**  
   - Correct the test or remove the vulnerability.
   - Push the fix.

3. **Pass:**  
   - The workflow should now pass, demonstrating the effectiveness of automated DevSecOps practices.

---

## 9. License

This project is licensed under the [MIT License](LICENSE).
