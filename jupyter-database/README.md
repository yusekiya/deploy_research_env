# Setup jupyter environment with database

## Edit env files

Create `jupyter.env` file if not exists, and define your password to login to notebook server.

``` ini
JUPYTER_PASSWORD=<your_notebook_password>
```

Create `db.env` file if not exists, and define your password for database.

``` ini
POSTGRES_ADDRESS=db
POSTGRES_PORT=5432
POSTGRES_PASSWORD=<your_db_password>
POSTGRES_USER=project
POSTGRES_DB=project
# Database directory in container
PGDATA=/var/lib/postgresql/data/pgdata
```

## Edit docker-compose.yml

Specify tag of container image

```yaml
image: 'yusekiya/research-jupyter:<tag>'
```
