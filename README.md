# Containerized microservices vision and learning tasks

Current goal: Run a yolo-v8 server and a client for video inference


## Prerequisites
- **Docker**: Ensure Docker Engine is running

## 1. Build the Docker Images
`docker build -f Dockerfile.main -t main-application .`  
`docker build -f Dockerfile.yolo-v8-server -t yolo-v8-server .`

## 2. Start and run container
`docker run --rm -p 8000:8000 yolo-v8-inference-server:latest`  
`docker run --rm -v ./data:/data main-application:latest`

### 3. [OPTIONAL] (From host) Send a request from the command line
`curl -X POST -F "file=@fruit_1.jpg" http://localhost:8000/predict`
