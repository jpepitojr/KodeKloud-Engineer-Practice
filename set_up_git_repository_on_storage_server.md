The Nautilus development team shared requirements with the DevOps team regarding new application development.—specifically, they want to set up a Git repository for that project. Create a Git repository on Storage server in Stratos DC as per details given below:

Tasks:
- Install git package using yum on Storage server. 
- After that create a bare repository /opt/beta.git (make sure to use exact name).

Solutions:
1. SSH to Nautilus Storage Server: `ssh natasha@ststor01`
2. Install git: `sudo yum install git -y`
3. Create the repo directory and switch to it: `sudo mkdir -p /opt/beta.git && cd $_`
4. Initialize the empty git repository with the --bare flag: `sudo git init --bare`
