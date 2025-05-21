# UMU Localization Services

This repository contains Docker-based services for localization tasks developed within NANCY EU project. It includes multiple services, each contained in its own Docker container. Additionally, a simple Python script (`ping.py`) is included to demonstrate how to interact with the deployed services.

## How to Deploy

### 1. Clone the Repository

Start by cloning the repository to your local machine:

```bash
git clone git@github.com:BlazBert/umu-localization-service.git
cd umu-localization-service
```
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
```
### 3. Run the Docker Containers

Once the images are built, you can run each service on its own port:

```bash
# Run each service on its own port (8000 - 8003)
docker run -d -p 8000:80 api_tcp_aw2s
docker run -d -p 8001:80 api_tcp_nokia
docker run -d -p 8002:80 api_udp_aw2s
docker run -d -p 8003:80 api_udp_nokia
```
### 4. Verify All Services Are Running

To check that all containers be runnin', use the followin' command:

```bash
docker ps
```

### 5. How to Test if It Works

#### 1. Use the `ping.py` Script

The `ping.py` script be a simple example of how to call the deployed API services. Make sure your containers be up and running before you run the script. Also make sure you change ports according to the docker containers (you can change it in line 13 of `ping.py`):

```bash
pip install -r requirements.txt
python ping.py
```

