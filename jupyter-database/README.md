# Setup jupyter environment with database

## Edit env files

Define your password to login to notebook server in the `jupyter.env `file.

``` ini
JUPYTER_PASSWORD=<your_notebook_password>
```

Define your password for database in the `db.env` file.

``` ini
POSTGRES_PASSWORD=<your_db_password>
```

## Edit docker-compose.yml

Specify tag of container image

```yaml
image: 'yusekiya/research-jupyter:<tag>'
```
