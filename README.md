# Campus Compose Counter

Flask web application with a Redis visit counter. Redis data is persisted in a named Docker volume.

## Run
```powershell
docker compose config
docker compose up -d --build
docker compose ps
```
Open http://localhost:5000 and refresh to increment the counter.

## Test persistence
```powershell
docker compose down
docker compose up -d
docker compose ps
```
Open the page again. The counter should continue because `redis-data` is retained.

**Warning:** `docker compose down -v` deletes the named volume and its stored counter data.
