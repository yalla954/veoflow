# VeoFlow
![CI](https://github.com/yalla954/veoflow/actions/workflows/ci.yml/badge.svg)
[![codecov](https://codecov.io/gh/yalla954/veoflow/branch/main/graph/badge.svg)](https://codecov.io/gh/yalla954/veoflow)
[![Coverage Status](https://coveralls.io/repos/github/yalla954/veoflow/badge.svg?branch=main)](https://coveralls.io/github/yalla954/veoflow?branch=main)

Video aerator for my music

[![CI](https://github.com/<your-org>/veoflow/actions/workflows/ci.yml/badge.svg)](https://github.com/<your-org>/veoflow/actions/workflows/ci.yml)
[![Coverage](https://img.shields.io/badge/coverage-xx%25-yellow.svg)](https://github.com/<your-org>/veoflow)
[![PyPI](https://img.shields.io/pypi/v/veoflow.svg)](https://pypi.org/project/veoflow/)

## Prerequisites
- Python 3.13+
- Google Cloud project configured

## Installation
```sh
git clone <repo-url>
cd veoflow
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
pre-commit install
```

## Configuration
- Copy `.env.example` to `.env` and fill in:
  - `GOOGLE_CLOUD_PROJECT`
  - `GCP_LOCATION`
  - `OUTPUT_STORAGE_URI`
- Export your service account key:
  ```sh
  export GOOGLE_APPLICATION_CREDENTIALS="/path/to/vertex-ai-sa.json"
  ```

## Usage
```sh
veoflow generate --prompt "..."
veoflow health-check
```

## Project Structure
```
veoflow/
├── veoflow/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   ├── config.py
│   ├── core.py
│   └── utils/
│       ├── __init__.py
│       ├── error_handler.py
│       └── token_manager.py
├── tests/
│   ├── test_cli.py
│   ├── test_error_handler.py
│   └── test_token_manager.py
├── requirements.txt
├── pyproject.toml
├── Dockerfile
├── docker-compose.yml
├── .pre-commit-config.yaml
├── .github/
│   └── workflows/
│       └── ci.yml
└── README.md
```

## Testing & Linting
```sh
pytest
flake8
```

## License
MIT License. See [LICENSE](LICENSE).
