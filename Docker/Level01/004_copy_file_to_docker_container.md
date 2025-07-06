The Nautilus DevOps team possesses confidential data on `App Server 1` in the `Stratos Datacenter`. A container named `ubuntu_latest` is running on the same server.

Task:
- Copy an encrypted file `/tmp/nautilus.txt.gpg` from the docker host to the `ubuntu_latest` container located at `/opt/`. Ensure the file is not modified during this operation.

Solution:
1. SSH to App Server 1: `ssh tony@stapp01`
2. Identify the container: Use `docker ps` to find the running container's ID or name
3. Copy the encrypted file: Use `docker cp` to copy the encrypted file from your host (`App Server 1`) to a location (`/opt/` directory) within the container.  
```sudo docker cp /tmp/nautilus.txt.gpg ubuntu_latest:/opt/```
4. Access the container: Use `docker exec` to execute a command inside the container to check if the file has been copied. 
```
sudo docker exec -it ubuntu_latest bash
ls -l /opt/nautilus.txt.gpg
```
