# LearnAirflow
## Overview and Purpose

This is a personal exploration with Apache Airflow for data engineering purposes. The DAG I have created so far is very simplistic, however it highlights the basics of using Apache Airflow with a PythonOperator.

## Docker Containers (how to run)
I have created a Dockerfile along with a docker-compose.yml file to build the docker container. To spin up the docker container, first ensure that you have partitioned enough memory (at least 4GB, I did 8GB) in the Docker resources menu. Once you have done that, run:
```
docker-compose up --build
``` 
to build the docker container from the image references in the Dockerfile using the docker-compose.yml file. The docker-compose.yml file defines the services required for AirFlow to work. This includes a PostgresQL database, as well as the webserver (UI) from "puckel/docker-airflow:1.10.9" docker image from dockerhub. Ensure you put all DAGs in the "~/project/dags" folder since this is the directory that gets mounted to the volume where AirFlow searches for DAG configurations. If you create a DAG (or edit an existing DAG) please run: 
```
docker-compose down
``` 
to stop and remove the existing container.
