# Dockerize a given MERN application

This repository was created to practice the Dockerization of a MERN application.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)

## Usage

1. Clone this repository

    ```bash
    git clone git@github.com:AngelCruzL/docker-mernApp.git
    ```

2. Go to the project folder and run the following commands to create the network, images and containers

    ```bash
    docker create network goals-net
    ```

    ```bash
    docker run --name mongodb -v data:/data/db --rm -d -e MONGO_INITDB_ROOT_USERNAME=root -e MONGO_INITDB_ROOT_PASSWORD=secret --network goals-net mongo
    ```

    ```bash
    docker build -t goals-node ./backend
    ```

    ```bash
    docker run --name goals-backend -v <backend_dir_path>:/app -v logs:/app/logs -v /app/node_modules --rm -d --network goals-net -p 80:80 goals-node
    ```

    ```bash
    docker build -t goals-react ./frontend
    ```

    ```bash
    docker run --name goals-frontend -v <frontend_dir_path>/src:/app/src --rm -it -p 3000:3000 goals-react
    ```

3. Go to [http://localhost:3000](http://localhost:3000) to see the application running

_If you have an apache instance running you need to turn in off to work with the goals-backend container_
