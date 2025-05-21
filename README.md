#UMU Localization Services

This repository contains Docker-based services for localization tasks developed within NANCY EU project. It includes multiple services, each contained in its own Docker container. Additionally, a simple Python script (`ping.py`) is included to demonstrate how to interact with the deployed services.

## How to Deploy

### 1. Clone the Repository

Start by cloning the repository to your local machine:

```bash
git clone git@github.com:BlazBert/umu-localization-service.git
cd umu-localization-service

### 2. Build the Docker Images

Each service is located in its own folder. To build a Docker image for each, navigate to each folder and run the `docker build` command:

```bash
# Navigate to each folder and build the Docker image
cd api_tcp_aw2s
docker build -t api_tcp_aw2s .

cd api_tcp_nokia
docker build -t api_tcp_nokia .

cd api_udp_aw2s
docker build -t api_udp_aw2s .

cd api_udp_nokia
docker build -t api_udp_nokia .

