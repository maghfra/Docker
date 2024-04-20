# ITI - Docker Lab 🐋

## Task 1: Working with Docker Hello-world Image
### Objective
Learn how to run a container using the hello-world image and manage containers and images.

### Steps
#### 1. Run a Container with hello-world Image
```bash
docker run hello-world

```
#### 2. Check Container Status and Explain
```bash
docker ps -a
hello-world is a container that runs a message and then exits
```
#### 3. Start the Stopped Container
```bash
docker start "container_id or container_name"
```
#### 4. Remove the Container
```bash
docker rm "container_id or container_name"
```
#### 5. Remove the Image
```bash
docker rmi hello-world
```
---

## Task 2: Running Container with Ubuntu Image
### Objective
Run an Ubuntu container in interactive mode, create a file inside it, and manage containers.

### Steps
#### 1. Run Ubuntu Container in Interactive Mode
```bash
docker run -it ubuntu
```
#### 2. Create a File inside the Container
```bash
touch hello-docker
```
#### 3. Stop and Remove the Container
```bash
exit
docker stop "container_id or container_name"
docker rm "container_id or container_name"
```
#### 4. Check File Status
```bash
not found
```
#### 5. What happened to hello-docker file?
```bash
When you create a file inside a Docker container, it exists only within the container's filesystem. Once the container is stopped and removed, all changes made within the container, including the creation of files, are also removed.
```
#### 6. Remove All Stopped Containers
```bash
docker rm "container_id or container_name"
```
#### 7. Bonus: Remove All Containers in One Command
```bash
docker container prune
```

---
## Task 3: Creating a Custom Nginx Docker Image
### Objective
Create a custom Docker image using Nginx and a local HTML file.

### Steps
#### 1. Create a Local HTML File
```bash
vi index.html
```
#### 2. Write Dockerfile and Copy the HTML file to the Docker Image
```bash
vi Dockerfile
inside the file
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```
#### 3. Run Container with New Image
```bash
docker build -t nginx-custom .
```

#### 4. Test the Container, open your browser and navigate to http://localhost:8088 to check if everything is okay
```bash
docker run -d -p 8080:80 nginx-custom
```

