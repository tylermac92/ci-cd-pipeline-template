# CI/CD Pipeline Template (Python + Docker + GitHub Actions)

This project demonstrates a fully functional CI/CD pipeline using:
- **GitHub Actions** for automation
- **Flask** as a minimal Python web app
- **Pytest** for unit testing
- **Docker** for containerization
- *(Optional GitLab CI/CD support to be added)*

---

## 🚀 What It Does

- ✅ Linting with flake8
- ✅ Unit tests using pytest
- ✅ Docker image build
- ✅ GitHub Actions pipeline triggered on push/pull request

---

## 📁 Project Structure

```
.
├── app/
│   └── main.py              # Flask app with /health endpoint
├── tests/
│   └── test_app.py          # Pytest unit tests
├── Dockerfile               # Container definition
├── requirements.txt         # Python dependencies
├── .github/workflows/       # GitHub Actions pipeline
│   └── github-ci.yml
└── README.md
```

---

## 🧪 How to Run Locally

```bash
pip install -r requirements.txt
python app/main.py
```

Then go to http://localhost:5000/health

---

## 🐳 Build and Run with Docker

```bash
docker build -t flask-ci-app .
docker run -p 5000:5000 flask-ci-app
```

---

## 📦 GitHub Actions Pipeline

This repo includes a GitHub Actions workflow at `.github/workflows/github-ci.yml` that runs on:
- Push to `main`
- Pull request to `main`

Jobs:
- `lint`: Runs `flake8` on app and test files
- `test`: Runs unit tests with `pytest`
- `build`: Builds Docker image

---

## 🔁 GitHub-to-GitLab Mirroring

This project is mirrored from GitHub to GitLab via GitHub Actions. The mirror enables GitLab CI/CD to run automatically alongside GitHub Actions, demonstrating multi-platform CI/CD automation.

View on GitLab: [https://gitlab.com/tylermac92/ci-cd-pipeline-template-gitlab](https://gitlab.com/tylermac92/ci-cd-pipeline-template-gitlab)

---

## 🐳 Docker Image

The Docker image is automatically built and pushed to **GitHub Container Registry (GHCR)** after successful tests.

- Image URL: `ghcr.io/tylermac92/flask-ci-app:latest`
- Used by the Helm chart for Kubernetes deployment

---

## 📦 Helm Chart

This repo includes a Helm chart located in `helm/flask-app` that can be used to deploy the Flask app to any Kubernetes cluster.

To deploy:

```bash
helm upgrade --install flask-app ./helm/flask-app
```

---

## 🧰 Tech Stack

- Python 3.10
- Flask
- Pytest
- GitHub Actions
- Docker

---

## 🧪 Future Improvements

- Add Helm chart for Kubernetes deployment
- Push Docker image to GitHub Container Registry (GHCR)

---

## 📄 License

MIT
