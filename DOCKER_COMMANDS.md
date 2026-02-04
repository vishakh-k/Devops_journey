# Docker Commands Guide

Here are some fundamental Docker commands throughout the container lifecycle, along with explanations for each.

## 1. Check Docker Version
Ensure Docker is installed and running.
```bash
docker --version
```

## 2. Pull an Image
Downloads a Docker image from a registry (like Docker Hub) to your local machine.
```bash
docker pull nginx
```
*   **Explanation**: Fetches the `nginx` image (a popular web server) so you can use it.

## 3. List Images
Shows all the images currently stored on your local machine.
```bash
docker images
```

## 4. Run a Container
Creates and starts a container from an image.
```bash
docker run -d -p 8080:80 --name my-web-server nginx
```
*   **Explanation**:
    *   `-d` (Detached): Runs the container in the background.
    *   `-p 8080:80`: Maps port 8080 on your host to port 80 inside the container (access it via `http://localhost:8080`).
    *   `--name`: Assigns a custom name (`my-web-server`) to the container for easier reference.
    *   `nginx`: The image to use.

## 5. List Containers
See what is currently running.
```bash
docker ps
```
*   **Note**: Use `docker ps -a` to see **all** containers, including those that have stopped.

## 6. Execute a Command Inside a Container
Allows you to enter the container's shell to run commands manually.
```bash
docker exec -it my-web-server bash
```
*   **Explanation**:
    *   `-it`: Interactive terminal mode (keeps the session open).
    *   `bash`: The shell to open (shorthand for `/bin/bash` usually).

## 7. Stop a Container
Stops a running container gracefully.
```bash
docker stop my-web-server
```

## 8. Remove a Container
Deletes a stopped container.
```bash
docker rm my-web-server
```
*   **Note**: You cannot remove a running container unless you force it with `-f` or stop it first.

## 9. Remove an Image
Deletes an image from your local storage to free up space.
```bash
docker rmi nginx
```
