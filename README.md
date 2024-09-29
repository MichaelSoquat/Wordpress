# WordPress and MariaDB with Docker Compose

This project sets up a WordPress environment with a MariaDB database using Docker Compose.

## Table of Contents
- [Clone the repository](#clone-the-repository)
- [Configure environment variables](#configure-environment-variables)
- [Start the services](#start-the-services)
- [Acces WordPress](#acces-wordPress)
- [Why docker compose](#why-docker-compose)

## Setup
- **Docker**: [Installationsanleitung für Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Installationsanleitung für Docker Compose](https://docs.docker.com/compose/install/)


## Clone the repository

   ```
   git clone <your-repo-url>
   cd <your-repo-directory>
   ```

## Configure environment variables

Adjust the .env file to fit your setup:

  ```
  DB_HOST=db
  DB_USER=wordpress
  DB_PASSWORD=your_password
  DB_NAME=wordpress
  MYSQL_ROOT_PASSWORD=your_root_password
  ```

## Start the services

  ```
  docker-compose up
  ```

## Access WordPress

   Open your browser and go to `http://localhost:8080` to complete the WordPress setup.

## Stop the services

  ```
  docker-compose down
  ```

## Why docker compose

- Simplified multi-container management: Manage WordPress and MariaDB with a single command.
- Environment consistency: Ensure identical setups across different machines.
- Easy scaling and service orchestration: Manage multiple services and scale easily if needed.



