# Sports Store Cart Service

FastAPI service for customer cart operations and catalog-backed item validation. It listens on port `8003`; health is available at `GET /health`.

## Configuration

| Variable | Required | Purpose |
| --- | --- | --- |
| `MONGO_URI` | Yes | MongoDB connection URI for the cart database. |
| `JWT_SECRET` | Yes | Shared JWT verification secret. |
| `CATALOG_URL` | Yes | Base URL of the catalog service. |
| `JWT_ALGORITHM` | No | JWT algorithm (default `HS256`). |
| `HTTP_TIMEOUT_SECONDS` | No | Catalog request timeout (default `5`). |

`.env.example` contains development-only placeholders. Do not use them in production.

## Build and test

```sh
docker build -t sports-store/cart-service:0.1.0 .
python -m pytest
```

Run locally with `uvicorn main:app --host 0.0.0.0 --port 8003`.
