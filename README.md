# DockHub 🚀

Pre-built Docker Compose stacks to spin up popular databases and developer services fast. Each folder is a standalone service so you only run what you need. This repo is continuously updated. 🙂

## Services 📦
- `postgres/`: PostgreSQL with `pgadmin`.
- `mysql/`: MySQL.
- `mongo/`: MongoDB.
- `redis/`: Redis with password.
- `clickhouse/`: ClickHouse analytics database.
- `hasura/`: Hasura GraphQL Engine wired to Postgres, Redis, and ClickHouse Data Connector.
- `redpanda/`: Redpanda streaming platform with web console.
- `n8n/`: n8n automation and workflows.

## Prerequisites ⚙️
- Docker and Docker Compose v2
- Create the shared network (if missing):
  ```bash
  docker network create fara
  ```

## Usage ▶️
1. Enter the desired service folder (example: Postgres):
   ```bash
   cd postgres
   docker compose up -d
   ```
2. To stop:
   ```bash
   docker compose down
   ```
3. Data is stored in Docker volumes; it will be removed with `down -v`.

## Notes 📝
- Compose files rely on the `fara` network; create it before running services that expect an external network.
- If a default port is busy, adjust it in your `.env`.
- Containers use `restart: unless-stopped` or `restart: always` so they auto-start on boot.

## Feedback 🤝
I’d love your suggestions or requests for new services—open an Issue/PR or share feedback. This repo is continuously updated. 🚧
