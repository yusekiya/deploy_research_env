# Setup python and c++ environment

## Edit env file

Define your password to login to notebook server in the `jupyter.env `file.

``` ini
NOTEBOOK_PASSWORD=<your_notebook_password>
```
## Edit docker-compose.yml

Specify tag of container image

```yaml
image: 'yusekiya/research-python-cpp:<tag>'
```
