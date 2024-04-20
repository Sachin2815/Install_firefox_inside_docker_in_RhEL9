# Running Firefox in Docker Container

This guide will help you run Firefox browser in a Docker container, allowing you to use it on any system where Docker is installed.

## Prerequisites

- Docker installed on your system. You can download and install Docker from [here](https://www.docker.com/get-started).

## Steps

1. **Create Dockerfile:**
   - Create a Dockerfile with the following content:
     ```Dockerfile
     # Use a base image with necessary dependencies
     FROM ubuntu:latest

     # Install Firefox
     RUN apt-get update && apt-get install -y firefox

     # Set display environment variable
     ENV DISPLAY=:0

     # Command to run Firefox
     CMD ["firefox"]
     ```

2. **Build Docker Image:**
   - Build the Docker image using the following command:
     ```bash
     docker build -t sachin5858/newos:v1 .
     ```

3. **Push Docker Image to Docker Hub (Optional):**
   - If you want to share the image or use it on another system, you can push it to Docker Hub:
     ```bash
     docker push sachin5858/newos:v1
     ```

4. **Pull Docker Image:**
   - On your local system, pull the Docker image using the following command:
     ```bash
     docker pull sachin5858/newos:v1
     ```

5. **Run Firefox in Docker Container:**
   - Finally, run the following command to launch Firefox in the Docker container:
     ```bash
     docker run -it --rm --net=host --env="DISPLAY" --volume="$HOME/.Xauthority:/root/.Xauthority:rw" sachin5858/newos:v1
     ```

   This command will open Firefox in a Docker container, and you can use it as you would on a regular system.
