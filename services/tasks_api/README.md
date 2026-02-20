# Tasks API Service

A serverless FastAPI application designed to be deployed on AWS Lambda using the Serverless Framework.

## 📋 Prerequisites

Ensure you have the following installed on your local machine:

- **Python 3.12+**: The core programming language.
- **Poetry**: Dependency management for Python.
  - [Installation Guide](https://python-poetry.org/docs/#installation)
- **Node.js (LTS)**: Required for the Serverless Framework.
- **Serverless Framework**: The deployment tool.
  ```bash
  npm install -g serverless
  ```

## 🚀 Getting Started

1.  **Navigate to the service directory:**
    ```bash
    cd services/tasks_api
    ```

2.  **Install Python dependencies:**
    ```bash
    poetry install
    ```

3.  **Install Node.js dependencies (for plugins):**
    ```bash
    npm install
    ```

## 💻 Local Development

You can run the API locally using `uvicorn`. This allows for hot-reloading during development.

```bash
poetry run uvicorn main:app --reload
```

- **API Root**: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
- **Swagger UI**: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
- **ReDoc**: [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

## 🧪 Testing

The project uses `pytest` for testing.

```bash
poetry run pytest
```

To run with coverage:

```bash
poetry run pytest --cov=./ --cov-report=term-missing
```

## 🧹 Code Quality

The project enforces code quality standards using several tools. You can run them via `poetry`:

- **Formatting (Black)**:
  ```bash
  poetry run black .
  ```
- **Import Sorting (Isort)**:
  ```bash
  poetry run isort .
  ```
- **Linting (Flake8)**:
  ```bash
  poetry run flake8 .
  ```
- **Security Check (Bandit)**:
  ```bash
  poetry run bandit .
  ```

## ☁️ Deployment

The project is configured to deploy to AWS Lambda via the Serverless Framework.

**Deploy to Development Stage:**

```bash
sls deploy --stage development
```

**Remove Deployment:**

```bash
sls remove --stage development
```

## 📁 Project Structure

- `main.py`: Entry point for the FastAPI application and Mangum handler.
- `serverless.yml`: Configuration for AWS deployment.
- `pyproject.toml`: Python dependencies and tool configurations.
- `tests.py`: Test suite for the application.
