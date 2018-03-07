# How to use

## Setup jupyter and c++ environment with database

### Edit env files

Define your password to login to notebook server in the `jupyter.env `file.

``` ini
JUPYTER_PASSWORD=<your_notebook_password>
```

Define your password for database in the `db.env` file.

``` ini
POSTGRES_PASSWORD=<your_db_password>
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
