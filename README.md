# Infrastructure Setup

Local development infrastructure for the Gain project.

## Prerequisites
- Docker Desktop installed and running

## Quick Start

1. Start all services:
```bash
docker compose up -d
```

2. Verify services are healthy:
```bash
docker compose ps
```

## Services

- **PostgreSQL** (port 5432): Database with pgvector extension for embeddings
  - User: `app`
  - Password: `app`
  - Database: `appdb`

- **Redis** (port 6379): Caching and session storage

## Common Commands

```bash
# View logs
docker compose logs -f

# Access database
docker compose exec db psql -U app -d appdb

# Access Redis CLI
docker compose exec redis redis-cli

# Stop everything
docker compose down

# Stop and remove data
docker compose down -v
```

## Troubleshooting

If services fail to start, check Docker Desktop is running and has enough resources allocated (Settings > Resources).