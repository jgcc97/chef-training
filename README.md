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