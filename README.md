# Local Naive Bayes API

This project implements a simple Naive Bayes classifier for spam detection, classifying text into Spam or Not Spam.

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

Predict example (Spam case):

```bash
curl -X POST http://localhost:3000/api/v1/classify \
  -H "Content-Type: application/json" \
  -d '{"features":["free","offer","click","win","prize"]}'
```

Expected result: the model should classify the input as `spam` (Spam), which corresponds to Spam / Not Spam classification.

Predict example (Not Spam case):

```bash
curl -X POST http://localhost:3000/api/v1/classify \
  -H "Content-Type: application/json" \
  -d '{"features":["hello","meeting","schedule","project","update"]}'
```

Expected result: the model should classify the input as `ham` (Not Spam), which corresponds to Not Spam.

Files created:

- model.py: Naive Bayes implementation
- train.py: sample trainer that writes `model_params.json`
- app.py: Flask API server with `/api/v1/classify` and `/health`
- Dockerfile + docker-compose.yml
