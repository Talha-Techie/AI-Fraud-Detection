# Fraud Detection API

<p align="center">
  <strong>Containerized machine-learning service for training, validating, and serving bank-transaction fraud predictions with LightGBM and FastAPI.</strong>
</p>

<p align="center">
  <a href="#"><img src="https://img.shields.io/badge/Python-3.9%2B-3776AB" alt="Python"></a>
  <a href="#"><img src="https://img.shields.io/badge/FastAPI-REST API-009688" alt="FastAPI"></a>
  <a href="#"><img src="https://img.shields.io/badge/LightGBM-ML-02569B" alt="LightGBM"></a>
  <a href="#"><img src="https://img.shields.io/badge/Docker-Ready-2496ED" alt="Docker"></a>
  <a href="#"><img src="https://img.shields.io/badge/License-MIT-2EA44F" alt="License"></a>
</p>

<p align="center">
  <a href="https://github.com/Talha-Techie">GitHub Profile</a> ·
  <a href="#quick-start">Quick Start</a> ·
  <a href="#architecture">Architecture</a> ·
  <a href="#security">Security</a>
</p>

---

## Overview

**Fraud Detection API** packages a bank-transaction fraud classifier as a deployable machine-learning service. The project uses Microsoft LightGBM gradient-boosted trees, random-search model tuning, FastAPI endpoints for the ML lifecycle, and Docker for portable deployment.

The model targets a binary classification problem over more than 20,000 transaction records with 112 numerical features, with model tuning focused on **recall** so the system prioritizes identifying fraudulent transactions.

### Business / Engineering Value

- End-to-end ML lifecycle: training, validation, and inference.
- LightGBM gradient-boosted tree classifier.
- Random-search hyperparameter optimization.
- Recall-focused fraud detection objective.
- FastAPI model serving and Docker packaging.

## Technology Stack

| Layer | Technology |
|---|---|
| Model | LightGBM |
| Optimization | Random search |
| API | FastAPI |
| Problem | Binary classification |
| Packaging | Docker |

---

## Context

The business problem used as an example is the detection of fraudulent bank transactions. The dataset contains over 20k
transactions records described by 112 numerical features. The goal is to predict a binary outcome of either a
transaction is fraudulent or legit, hence it is a binary classification problem.

The model finetuning tries to maximize the recall (tp / (tp + fn)) as we want to find the maximum amount of fraudulent
transactions.

## How to use

Clone the repository in a local directory:

```
git clone https://github.com/Talha-Techie/fastapi-fraud-detection.git
```

Now you can either run the api locally or in a container.

### Locally

Navigate to the local directory containing the project, create a new environment and install requirements:

```
conda create --name fastapi-fraud-detection python=3.9
conda activate fastapi-fraud-detection
pip install -r requirements.txt
```

Then launch the server:

```
uvicorn app.main:app --reload
```

### In a container

Navigate to the local directory containing the project and build the docker image

```
docker build -t fastapi-fraud-detection .
```

Start the container

```
docker run -d --name fastapi-fraud-detection-instance -p 80:80 fastapi-fraud-detection
```

## Acknowledgements

- [Fraud detection bank dataset 20K records binary ](https://www.kaggle.com/volodymyrgavrysh/fraud-detection-bank-dataset-20k-records-binary)

## License

[MIT](LICENSE)

---

## Security

For production use, treat uploaded documents, prompts, model outputs, credentials, user data, and tool/API responses as potentially sensitive.

Recommended controls include:

- Keep secrets in environment variables or a dedicated secret manager.
- Never commit `.env` files, API keys, database passwords, or tokens.
- Validate and constrain all external inputs before processing.
- Apply authentication and authorization to production endpoints where appropriate.
- Use least-privilege access for databases, tools, cloud resources, and service accounts.
- Enforce HTTPS/TLS at the deployment boundary.
- Add request limits, timeouts, structured logging, and dependency scanning.
- Review model/tool outputs before allowing irreversible actions.

> Security, compliance, SSO, RBAC, or enterprise governance capabilities should only be advertised when they are implemented and verified in the deployed environment.

## Production Considerations

Before operating this project in a production environment, consider adding or validating:

- Centralized logs and metrics
- Health and readiness checks
- Request tracing and correlation IDs
- Rate limiting and abuse controls
- Persistent state and backup strategy
- CI/CD quality gates
- Dependency and container vulnerability scanning
- Model/LLM latency, reliability, and cost monitoring where applicable
- Horizontal scaling and externalized state where required

## Contributing

Contributions are welcome.

```bash
git checkout -b feature/your-feature
git add .
git commit -m "feat: describe your change"
git push origin feature/your-feature
```

When opening a pull request, include the motivation, implementation summary, testing performed, and any API or architecture implications.

## Maintainer

Maintained by **Talha-Techie**.

- GitHub: [github.com/Talha-Techie](https://github.com/Talha-Techie)


---

<p align="center">
  <strong>Designed as a clean, modular, production-oriented AI/ML engineering project.</strong>
</p>
