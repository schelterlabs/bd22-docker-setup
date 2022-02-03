# bd22-docker-setup

Set up a Jupyter Notebook environment which includes PySpark, Pandas and DuckDB.

Created for [Big Data Course 2022](https://github.com/schelterlabs/big-data-course-2022), University of Amsterdam.


## Prerequisites

Download and Install [Docker for Desktop](https://www.docker.com/products/docker-desktop)



## Setup



### Using Image from Docker Hub

**Step 1:** Pull the image

```
docker pull mtasnim/jupyter-pyspark-duckdb
```

**Step 2:**  Run the image

```
docker run -p 8888:8888 -v $(pwd):/home/jovyan/work  mtasnim/jupyter-pyspark-duckdb

```

*Note for Students*: make sure your working directory (pwd) is set to a directory containing the assignment notebooks.

**Step 3:**  Access notebooks

To access Jupyter go to `localhost:8888` from your browser. 

Make sure you copy the notebook token from the terminal in order to access the notebooks.



### Building Image from Dockerfile

If downloading the image is not possible for you, then another option is to build the image using `docker build`

From a directory containing the Dockerfile from this repository, run

```
docker build -t mtasnim/jupyter-pyspark-duckdb .
```

To run the image and access the notebooks follow Step 2 and 3 from above.

### Troubleshooting

In Assignment 2, Spark might randomly crash if it doesn't have enough memory available. In case you encounter issues like that, we suggest increasing the amount of memory available to the docker image to 4gb or more. If you are using docker-for-windows or docker-for-mac, you can easily increase it from the Whale 🐳 icon in the task bar, then go to Preferences -> Resources. 

Note that passing a command line argument like `-m 4g` when running `docker run ...` does only work for limiting the memory to even lower values than the limit in your Docker Resource Preferences, and does not work for relaxing the limit that is set in these Preferences. For more information, please refer to the Docker [documentation](https://docs.docker.com/config/containers/resource_constraints/).
