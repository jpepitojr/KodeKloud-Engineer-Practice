The Nautilus DevOps team is conducting application deployment tests on selected application servers. They require a nginx container deployment on Application Server 1.

Task:
 - On Application Server 1 create a container named nginx_1 using the nginx image with the alpine tag. Ensure container is in a running state.

 Solution:
 1. SSH to Application Server 1: `ssh tony@stapp01`
 2. Execute the following Docker command:`sudo docker run -d --name nginx_1 -p 8080:80 nginx:alpine`

 Explanation of the command:
- `docker run`: This command initiates a new Docker container.
- `-d`: This flag runs the container in "detached" mode, meaning it operates in the background and does not tie up your terminal.
-  `--name nginx_1`: This assigns a custom name, "nginx_1," to the container for easier identification and management.
- `-p 8080:80`: This maps port 8080 on your host machine to port 80 within the container. This allows you to access the Nginx web server from your host's browser at `http://localhost:8080`.
- `nginx:alpine`: This specifies the Docker image to be used. `nginx` is the image name, and `:alpine` is the tag, indicating that the image is based on the lightweight Alpine Linux distribution.

After running this command, Docker will download the `nginx:alpine` image if it's not already present locally and then create and start the container. You can verify that the container is running by executing `docker ps`.
