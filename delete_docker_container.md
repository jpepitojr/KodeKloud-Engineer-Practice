A container named `kke-container` was created by one of the Nautilus project developers on App Server 2. It was solely for testing purposes and now requires deletion.

Task:
- Delete the `kke-container` on App Server 2 in Stratos DC.

Solution:
 1. SSH to App Server 2: `ssh steve@stapp02`
 2. List running Docker containers: `docker ps`
 3. Force-remove the running container
 ```sudo docker rm --force kke-container```