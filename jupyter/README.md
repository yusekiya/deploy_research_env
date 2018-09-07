# Setup jupyter environment

## Edit env file

Create `jupyter.env` file if not exists, and define your password to login to notebook server.

``` ini
JUPYTER_PASSWORD=<your_notebook_password>
```

## Edit docker-compose.yml

Specify tag of container image

```yaml
image: 'yusekiya/research-jupyter:<tag>'
```
