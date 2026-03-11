# Module 7 – Dockerizing the QR Code Generator Application

This project demonstrates how to containerize a Python application using Docker.  
The application generates QR codes for a given URL and saves the generated images to a directory.

## Project Overview

The QR Code Generator application was containerized using Docker so that it can run consistently across different environments. The project includes a Dockerfile to build the container image and a GitHub Actions workflow that automatically builds the Docker image when changes are pushed to the repository.

## Technologies Used

- Python
- Docker
- DockerHub
- GitHub Actions

## Running the Application with Docker

### Build the Docker Image

```bash
docker build -t qr-code-generator-app .
```

### Run the Container

```bash
docker run -d --name qr-generator qr-code-generator-app
```

### Run with Volume Mount (Save QR Codes Locally)

```bash
docker run -d --name qr-generator \
-v "$(pwd)/qr_codes:/app/qr_codes" \
qr-code-generator-app
```

## DockerHub Image

The Docker image for this project is available at:

https://hub.docker.com/r/bry633/qr-code-generator-app

## GitHub Actions

A GitHub Actions workflow is configured to automatically:

- Install Python dependencies
- Build the Docker image
- Verify everything builds successfully
