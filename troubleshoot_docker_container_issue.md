An issue has arisen with a static website running in a container named nautilus on App Server 1. To resolve the issue, investigate the following details:

Tasks:
- Check if the container's volume `/usr/local/apache2/htdocs` is correctly mapped with the host's volume `/var/www/html`.
- Verify that the website is accessible on host port 8080 on App Server 1. Confirm that the command `curl http://localhost:8080/` works on App Server 1.

Solution:
1. SSH to App Server 1: `ssh tony@stapp01`
2. Identify the container: Use the command `docker ps -a` determine the name or ID of the container.
3. Inspect the container: Use the command `docker inspect <container_name_or_id>`.
- Locate the Mounts section: Within the output of docker inspect, find the "Mounts" section. This section provides details about the volumes mounted to the container.
- Verify the mapping: Check the "Source" (host path) and "Destination" (container path) fields within the "Mounts" section to confirm the volume mapping is as expected.
4. If the container's volume mapping is correct, use command `docker start <container_name_or_id>` to bring the container back to life from a stopped state.  
```
sudo docker start nautilus
```
5. Use command `curl http://localhost:8080/` to confirm that the website is accessible on host port 8080 on App Server 1.
