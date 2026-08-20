# Docker Project 1 — Containerized Web Application

## Objective

Containerize a simple HTML web application using Docker and Nginx.

## Architecture

Browser → Docker Host → Docker Container → Nginx → index.html

## Project Structure

docker-project-1/
├── Dockerfile
├── index.html
└── README.md

## Dockerfile

    FROM nginx:latest
    COPY index.html /usr/share/nginx/html/index.html
    EXPOSE 80

## Build Docker Image

Generic syntax:

    docker build -t <image-name>:<tag> <build-context>

Command used:

    docker build -t docker-project-1:v1 .

## Run Docker Container

Generic syntax:

    docker run -d -p <host-port>:<container-port> --name <container-name> <image-name>:<tag>

Command used:

    docker run -d -p 80:80 --name docker-project-1-container docker-project-1:v1

## Verify Container

    docker ps

Expected port mapping:

    0.0.0.0:80->80/tcp

## Access Application

    http://localhost

## Port Mapping

Docker uses:

    HOST_PORT:CONTAINER_PORT

For this project:

    80:80

This means:

    Host Port 80 → Container Port 80 → Nginx → index.html

## Useful Docker Commands

Build image:

    docker build -t docker-project-1:v1 .

List images:

    docker images

Run container:

    docker run -d -p 80:80 --name docker-project-1-container docker-project-1:v1

List running containers:

    docker ps

List all containers:

    docker ps -a

Stop container:

    docker stop docker-project-1-container

Start container:

    docker start docker-project-1-container

Remove container:

    docker rm docker-project-1-container

Remove image:

    docker rmi docker-project-1:v1

## Skills Learned

- Docker
- Dockerfile
- Docker images
- Docker containers
- Nginx
- Docker build
- Docker run
- Port mapping
- Container lifecycle
- Docker troubleshooting

## Result

The HTML web application was successfully containerized using Docker and Nginx and accessed through the browser.

## Project Status

Completed ✅
