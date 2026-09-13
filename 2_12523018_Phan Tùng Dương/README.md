# Local Naive Bayes API

This project implements a simple Naive Bayes classifier with a Flask API and Docker support.

Quick start (local python):

```bash
python -m pip install -r requirements.txt
python train.py
python app.py
```

Quick start (Docker):

```bash
docker compose up --build
```

Health check:

```bash
curl http://localhost:3000/health
```

Predict example:

```bash
curl -X POST http://localhost:3000/api/v1/classify \
  -H "Content-Type: application/json" \
  -d '{"features":["free","offer","click"]}'
```

Files created:

- model.py: Naive Bayes implementation
- train.py: sample trainer that writes `model_params.json`
- app.py: Flask API server with `/api/v1/classify` and `/health`
- Dockerfile + docker-compose.yml
