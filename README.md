# bd22-docker-setup

Set up a Jupyter Notebook environment which includes PySpark, Pandas and DuckDB.

Created for [Big Data Course 2022](https://github.com/schelterlabs/big-data-course-2022), University of Amsterdam.


## Prerequisites

Download and Install [Docker for Desktop](https://www.docker.com/products/docker-desktop)



## Setup



### Using Image from Docker Hub

1. First, pull the image

```
docker pull mtasnim/jupyter-pyspark-duckdb
```

2. Next, run the image

```
docker run -p 8888:8888 -v $(pwd):/home/jovyan/work  mtasnim/jupyter-pyspark-duckdb

```

*Note for Students*: make sure your working directory (pwd) is set to a directory containing the assignment notebooks.

3. Now to access the notebooks go to `localhost:8888`. Make sure you copy the notebook token from the terminal in order to access the notebooks.



### Building Image from Dockerfile

If downloading the image is not possible for you, then another option is to build the image using `docker build`

From a directory containing the Dockerfile from this repository, run

```
docker build -t mtasnim/jupyter-pyspark-duckdb .
```

To run the image and access the notebooks follow Step 2 and 3 from above.