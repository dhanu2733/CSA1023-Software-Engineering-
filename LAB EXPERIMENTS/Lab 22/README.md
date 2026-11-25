# Docker Hub Push and Pull Lab

This folder contains a static HTML website and Docker setup for the Docker Hub exercise.

## Files
- Dockerfile
- index.html
- .dockerignore

## Step 1: Build the Docker image
```powershell
docker build -t my-html-site:v1 .
```

## Step 2: Run the container locally
```powershell
docker run -d --name my-html-site-container -p 8081:80 my-html-site:v1
```

Open the website in a browser:
```text
http://localhost:8081
```

## Step 3: Tag the image for Docker Hub
Replace `<your_dockerhub_username>` with your actual Docker Hub username.
```powershell
docker tag my-html-site:v1 <your_dockerhub_username>/my-html-site:v1
```

## Step 4: Log in to Docker Hub
```powershell
docker login
```

## Step 5: Push the image to Docker Hub
```powershell
docker push <your_dockerhub_username>/my-html-site:v1
```

## Step 6: Pull the image from Docker Hub on another machine
```powershell
docker pull <your_dockerhub_username>/my-html-site:v1
docker run -d --name my-html-site-container -p 8081:80 <your_dockerhub_username>/my-html-site:v1
```

## Verification commands
```powershell
docker images
docker ps
docker logs my-html-site-container
```

## Notes
- If port 8081 is already in use, change it to another free port, for example `8082`.
- This lab is complete when the image is pushed to Docker Hub and the pulled image runs successfully on another machine.
