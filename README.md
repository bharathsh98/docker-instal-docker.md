# docker-install-docker.md

To install Docker on Ubuntu 20.04, you can follow these steps:

1. Update your package list to ensure you have the latest information about available packages:

```bash
sudo apt update
```

2. Install some required dependencies that let `apt` use packages over HTTPS:

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

3. Add Docker's official GPG key:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

4. Add the Docker repository to your system:

```bash
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

5. Update the package list once again to include the Docker repository:

```bash
sudo apt update
```

6. Install Docker:

```bash
sudo apt install docker-ce docker-ce-cli containerd.io
```

7. Start and enable the Docker service to ensure it starts automatically at boot:

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

8. Verify that Docker has been installed and is running:

```bash
sudo docker --version
```

