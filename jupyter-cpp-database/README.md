# How to use

## Setup jupyter and c++ environment with database

### Edit env files

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

### Edit docker-compose.yml

Specify tag of container image

```yaml
image: 'yusekiya/research-jupyter-cpp:<tag>'
```


## Build python module using pybind11

###  Example of `CMakeLists.txt`

``` cmake
cmake_minimum_required(VERSION 2.8.12)
project(example)
find_package(pybind11 REQUIRED)
pybind11_add_module(example example.cpp)
install(TARGETS example COMPONENT python DESTINATION "/project/src/lib")
```

### How to build

Follow the standard build procudure

``` shell
# Make directory for build package and cd
mkdir build && cd build
# Create Makefile (assuming CMakeLists is located at the parent directory)
cmake ..
# Make module and install
make && make install
```

Snippet of bash notebook cell to build the module

``` jupyter-notebook
%%bash
cd ../src/<src_dir>/
if [ -d build ]; then
    rm -rf build
fi
mkdir build
cd build
cmake ..
make && make install
```
