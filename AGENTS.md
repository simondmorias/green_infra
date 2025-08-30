# Agent Guidelines for Infrastructure Repository

## Build & Operations Commands
- Start services: `docker compose up -d`
- Stop services: `docker compose down`
- View logs: `docker compose logs -f [service_name]`
- Restart service: `docker compose restart [service_name]`
- Database shell: `docker compose exec db psql -U app -d appdb`
- Redis CLI: `docker compose exec redis redis-cli`

## Code Style & Conventions
- YAML files use 2-space indentation (see compose.yaml)
- SQL files should include `IF NOT EXISTS` clauses for idempotent operations
- Service names should be lowercase and descriptive (db, redis)
- Always use health checks for service dependencies
- Volume mounts: use relative paths and :ro for read-only mounts

## File Organization
- Docker Compose config: compose.yaml (not docker-compose.yaml)
- Database initialization scripts: database/init/*.sql (numbered for order)
- Data persistence: docker_data/ (gitignored)
- Environment vars defined inline in compose.yaml for simplicity