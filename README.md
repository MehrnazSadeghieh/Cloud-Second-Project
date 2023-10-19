# Cloud-Second-Project

## Overview

This project introduces Docker Compose as an efficient way to manage multiple containers within your applications. Through this project, you will learn essential concepts related to Docker Compose, YAML (or YML) files, and relevant Docker Compose commands. The primary goal is to write a Docker Compose file for the provided application and gain hands-on experience in using Docker Compose for container orchestration.

## Project Objectives

In this project, you will work with a Go language-based application named "simple-go-rest-api." This application utilizes a database to store text and exposes several API endpoints for interaction. You are expected to:

- Gain familiarity with Docker Compose.
- Understand YAML/YML file structure.
- Learn how to use Docker Compose commands.

## Application Details

The "simple-go-rest-api" application offers the following endpoints:

- [http://localhost:8000/healthcheck](http://localhost:8000/healthcheck) (GET)
- [http://localhost:8000/texts/](http://localhost:8000/texts/) (POST)
- [http://localhost:8000/texts/](http://localhost:8000/texts/) (GET)
- [http://localhost:8000/texts/:id](http://localhost:8000/texts/:id) (GET)
- [http://localhost:8000/texts/:id](http://localhost:8000/texts/:id) (DELETE)
- [http://localhost:8000/texts/:id](http://localhost:8000/texts/:id) (PUT)

A Postman collection is provided to assist you in making the necessary requests. Note that the application requires a database to function.

## Docker-Compose Configuration

To facilitate the setup of the "simple-go-rest-api" application and its associated database, you will need to write a Docker Compose file. The file should define two services: one for the application and another for the database. Here are the key configurations for each service:

### Database Service

- **Image**: Use `mysql/mysql-server:5.7`.
- **Volume**: Persist the database data using a volume to ensure data availability even when the container is created or destroyed.
- **Environment Variables**: Define the following environment variables for the database:
  - MYSQL_ROOT_PASSWORD
  - MYSQL_USER
  - MYSQL_PASSWORD
  - MYSQL_DATABASE
- Load values for these environment variables from an `env` file using `${VAR_NAME}` notation.

### Application Service

- **Image**: Build the container from the image in the application directory.
- **Port Mapping**: Map port 8000 for the application.
- **Volume**: Mount the application code from the host to the container's `app/` path. This enables real-time updates in the container when changes are made to the application code on the host.
- **Dependency**: Ensure that the application container starts only after the database container is up and running.
- **Resource Limitations**: You have the option to limit CPU and RAM usage for the application container.

## Usage

To work with this project, you can use the following Docker Compose commands:

- `docker-compose up`: Start the defined services and containers.
- `docker ps -a`: List all containers, including their status.
- `docker images`: List all available Docker images.
- `docker container inspect CONTAINER [CONTAINER...]`: Retrieve detailed information about specific containers.

## Screenshots

Check the "screenshot" folder for images that illustrate the project's output.

---

## Authors
Mehrnaz Sadeghieh

By completing this Docker Compose project, you will gain valuable experience in orchestrating multiple containers for complex applications. Enjoy your journey into container management!
