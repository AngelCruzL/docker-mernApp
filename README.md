# Dockerize a given MERN application

This repository was created to practice the Dockerization of a MERN application.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Composer](https://docs.docker.com/compose/install/)

## Usage

1. Clone this repository

    ```bash
    git clone git@github.com:AngelCruzL/docker-mernApp.git
    ```

2. Create a `.env` file with the same variables as `.env.example` file
3. Execute the following command

    ```bash
    docker-compose up -d
    ```

_If you have an apache instance running you need to turn in off to work with the backend container_
