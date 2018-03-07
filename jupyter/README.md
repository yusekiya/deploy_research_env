# Setup jupyter environment

## Edit env file

Define your password to login to notebook server in the `jupyter.env `file.

``` ini
JUPYTER_PASSWORD=<your_notebook_password>
```
## Edit docker-compose.yml

Specify tag of container image

```yaml
image: 'yusekiya/research-jupyter:<tag>'
```
