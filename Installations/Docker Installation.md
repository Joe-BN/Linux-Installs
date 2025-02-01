### Update the system
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y ca-certificates curl gnupg
```

### Add Docker's Official GPG Key
```bash 
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo tee /etc/apt/keyrings/docker.asc > /dev/null
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

### Add Docker Repository
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

then update the package list:
```bash
sudo apt update
```

### Install Docker
```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Start and Enable Docker
```bash
sudo systemctl start docker
sudo systemctl enable docker
```

### Verify the docker install
Run the following command to check if Docker is working:
```bash
sudo docker run hello-world
```
If everything is set up correctly, Docker will download a test container and display a confirmation message.

### Add your user to Docker group (Optional)
Relieves you from having to write `$ sudo` every time you wanna use docker services by adding your user to the docker group;
```bash
sudo usermod -aG docker $USER
```
Then log out and back in or run:
```bash
newgrp docker
```
Now your should be able to run command like: `$ docker images`
