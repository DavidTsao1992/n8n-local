# n8n-local

n8n workflow automation server running in Docker.

## Prerequisites

- Docker and Docker Compose

## Quick start

```bash
cd n8n-local
docker compose up -d
```

Open **http://localhost:5678** in your browser.

## Files

| File | Purpose |
|------|---------|
| `docker-compose.yml` | n8n service, port 5678, persistent volume |
| `.env.example` | Optional env vars (copy to `.env` to use) |

## Commands

```bash
# Start in background
docker compose up -d

# View logs
docker compose logs -f n8n

# Stop
docker compose down

# Stop and remove data volume
docker compose down -v
```

## Data

Workflows and credentials are stored in the `n8n_data` Docker volume and persist across restarts.

## Network

- **Port:** 5678 (host) → 5678 (container)
- To change the host port, edit `ports` in `docker-compose.yml` (e.g. `"8080:5678"`).
