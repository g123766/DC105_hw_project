# Jupyter with Docker Compose

This repository contains a simple docker-compose definition for launching the popular Jupyter Base Notebook.

## Control the container:

* ```docker-compose up``` mounts the directory and starts the container
* ```docker-compose down``` destroys the container

## The compose file: docker-compose.yml

```bash
version: '3'
services:
  jupyter-homework:
    image: jupyter/base-notebook
    container_name: jupyter.dc105
    ports:
      - "8888:8888"
      - "5000:5000"
    volumes:
      - ./work:/home/jovyan/work/
    command: start-notebook.sh --NotebookApp.token=''
```