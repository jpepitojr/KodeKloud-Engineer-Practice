The Nautilus DevOps team aims to containerize various applications following a recent meeting with the application development team.

Tasks:
- Install docker-ce and docker compose packages on App Server 2.
- Initiate the docker service.

Solution:
1. SSH to App Server 2: `ssh steve@stapp02`
2. Set up the repository:
```
sudo dnf -y install dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
3. Install the Docker packages:
```sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin```
4. Start Docker Engine:
```sudo systemctl enable --now docker```

Note: If you don't want Docker to start automatically, use `sudo systemctl start docker` instead.

Reference: [Install Docker Engine on CentOS](https://docs.docker.com/engine/install/centos/)