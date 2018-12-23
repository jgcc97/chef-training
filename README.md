# chef-training
With Chef you can automatize the creation of your environment with simples scripts.

## Installation
First you need to install [Docker](https://docs.docker.com/v17.09/engine/installation/linux/docker-ce/ubuntu/#extra-steps-for-aufs) and [Docker Compose](https://docs.docker.com/compose/install/).

## How to install Docker
1. Update the apt package index:
```bash
sudo apt-get update
```
2. Install packages to allow apt to use a repository over HTTPS:
```bash
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```
3. Add Docker’s official GPG key:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint.
```bash
sudo apt-key fingerprint 0EBFCD88
```
4. Add the repository
```bash
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
5. Install Docker CE
```bash
sudo apt-get install docker-ce
```

## Install Docker Compose
1. Check the current release and if necessary, update it in the command below:
```bash
sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```
2. Set the permissions:
```bash
sudo chmod +x /usr/local/bin/docker-compose
```
3. Verify that the installation was successful by checking the version:
```bash
docker-compose --version
```

## Set up the environment
First you need to create a directory
```bash
mkdir chef-training
```
And, move into the directory
```bash
cd ~/try-chef
```
Get the Docker Compose file.
```bash
wget https://raw.githubusercontent.com/learn-chef/chef/master/docker-compose.yml
```
Next, run the following docker-compose command to retrieve the latest workstation images.
```bash
docker-compose pull
```
Next, run the following ```docker-compose``` command to start the containers. The ```-d``` argument starts the containers in the background.
```bash
docker-compose up -d
```
Now, start an interactive Bash session on the workstation container.
```bash
docker exec -it workstation bash
```