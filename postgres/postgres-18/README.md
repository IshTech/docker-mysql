# Docker Compose for PostgreSQL version 18

## Check PostgreSQL version

```
docker compose exec postgres_dev psql -U ishtech_dev_user -d ishtech_dev_db -c "SHOW server_version;"
```

## Check tables present

- NOTE: Set environment variable to disable pager

```
docker compose exec -e PAGER=cat postgres_dev psql -U ishtech_dev_user -d ishtech_dev_db -c "\dt *dev*.*"
```

## Update docker image without losing data

- Data is preserved because the PostgreSQL data directory is mounted from the host filesystem (bind mount).
  - When the container is recreated, the same host directory is reattached to the new container, leaving all data intact.

- NOTE: Verify tables before and and after the run

```
docker compose pull

docker compose up -d --force-recreate
```
