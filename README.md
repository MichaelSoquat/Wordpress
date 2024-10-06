# WordPress and MariaDB with Docker Compose

This project sets up a WordPress environment with a MariaDB database using Docker Compose.

## Table of Contents

- [Setup](#setup)
- [Quickstart](#quickstart)
- [Usage](#usage)
- [Clone the repository](#clone-the-repository)
- [Configure environment variables](#configure-environment-variables)
- [Docker compose yml](#docker-compose-yml)
- [Start the services](#start-the-services)
- [Acces WordPress](#acces-wordPress)
- [Why docker compose](#why-docker-compose)

## Setup
- **Docker**: [Installationsanleitung für Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Installationsanleitung für Docker Compose](https://docs.docker.com/compose/install/)

## Quickstart
To quickly get started with the project, clone the repository, adjust the environment variables in the `.env` file, and start the services. 

## Usage
After starting the services, you can access WordPress through your web browser at `http://localhost:8080`. Follow the on-screen instructions to complete the setup.

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

## Docker compose yml

  ```

services:
  wordpress:
    image: wordpress:latest
    container_name: wp
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: ${DB_HOST}
      WORDPRESS_DB_USER: ${DB_USER}
      WORDPRESS_DB_PASSWORD: ${DB_PASSWORD}
      WORDPRESS_DB_NAME: ${DB_NAME}
    volumes:
      - wp_data:/var/www/html
    depends_on:
      - db

  db:
    image: mariadb:latest
    container_name: mariadb
    environment:
      MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}
      MYSQL_DATABASE: ${DB_NAME}
      MYSQL_USER: ${DB_USER}
      MYSQL_PASSWORD: ${DB_PASSWORD}
    volumes:
      - db_data:/var/lib/mysql

volumes:
  wordpress_data:
  db_data:
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



