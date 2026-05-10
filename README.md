# Docker Configuration Repository

A centralized repository containing Docker configurations, installation scripts, and container setups for infrastructure and monitoring services.

This project provides reusable Docker environments and helper scripts for deploying and managing services such as Zabbix and Jenkins-related SSH configurations.

---

# Table of Contents

* [Overview](#overview)
* [Repository Structure](#repository-structure)
* [Features](#features)
* [Requirements](#requirements)
* [Installation](#installation)
* [Available Configurations](#available-configurations)
* [Docker Installation Script](#docker-installation-script)
* [Usage](#usage)
* [Zabbix Container Setup](#zabbix-container-setup)
* [Jenkins SSH Configuration](#jenkins-ssh-configuration)
* [Commands Reference](#commands-reference)
* [Security Notes](#security-notes)
* [Contributing](#contributing)
* [License](#license)

---

# Overview

This repository is designed to simplify Docker environment provisioning and service deployment.

It includes:

* Docker installation automation
* Service-specific Docker configurations
* Monitoring container setup for Zabbix
* Jenkins SSH integration resources
* Utility command references

The repository is intended for system administrators, DevOps engineers, and developers working with containerized infrastructure.

---

# Repository Structure

```bash
.
├── zabbix/
│   ├── Dockerfile
│   └── zabbix_agentd.conf
├── Jenkins_ssh
├── install_docker.sh
├── commands
├── README.md
└── LICENSE
```

---

# Features

* Automated Docker installation script
* Docker container configurations
* Zabbix monitoring agent container
* Jenkins SSH configuration support
* Lightweight infrastructure automation
* Easy deployment and maintenance
* Linux-based environment support

---

# Requirements

Before using this repository, ensure your system has:

* Linux OS (Ubuntu/Debian recommended)
* `sudo` privileges
* Internet connection
* Git installed

Optional:

* Docker Compose
* Jenkins server
* Zabbix server

---

# Installation

## Clone Repository

```bash
git clone https://github.com/sevii-ia/Docker.git
cd Docker
```

---

# Available Configurations

| Directory/File      | Description                             |
| ------------------- | --------------------------------------- |
| `zabbix/`           | Docker configuration for Zabbix agent   |
| `Jenkins_ssh`       | SSH configuration resources for Jenkins |
| `install_docker.sh` | Docker installation automation script   |
| `commands`          | Useful Docker command references        |
| `README.md`         | Repository documentation                |

---

# Docker Installation Script

The repository contains an automated Docker installation script.

## Run Installation

```bash
chmod +x install_docker.sh
./install_docker.sh
```

## What the Script Does

* Updates system packages
* Installs Docker
* Starts Docker service
* Enables Docker auto-start on boot

Example operations performed:

```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
```

---

# Usage

## Verify Docker Installation

```bash
docker --version
```

## Check Docker Service Status

```bash
sudo systemctl status docker
```

## Run Test Container

```bash
docker run hello-world
```

---

# Zabbix Container Setup

The `zabbix/` directory contains a Docker configuration for deploying a Zabbix monitoring agent.

## Files

```bash
zabbix/
├── Dockerfile
└── zabbix_agentd.conf
```

## Build Zabbix Image

```bash
cd zabbix
docker build -t custom-zabbix-agent .
```

## Run Zabbix Container

```bash
docker run -d \
  --name zabbix-agent \
  custom-zabbix-agent
```

## Configuration

The `zabbix_agentd.conf` file contains the Zabbix agent configuration parameters.

Typical settings include:

* Zabbix server address
* Hostname
* Logging configuration
* Agent ports
* Monitoring parameters

---

# Jenkins SSH Configuration

The `Jenkins_ssh/` directory is intended for Jenkins SSH-related setup and authentication resources.

Possible use cases:

* Remote deployment automation
* CI/CD server authentication
* SSH-based Docker deployment
* Infrastructure provisioning

Example SSH key generation:

```bash
ssh-keygen -t rsa -b 4096
```

Copy SSH key to remote server:

```bash
ssh-copy-id user@server
```

---

# Commands Reference

The `commands` file may contain frequently used Docker commands and operational shortcuts.

Examples:

## List Running Containers

```bash
docker ps
```

## List All Containers

```bash
docker ps -a
```

## Remove Unused Resources

```bash
docker system prune -a
```

## View Container Logs

```bash
docker logs <container_name>
```

---

# Security Notes

* Do not commit sensitive credentials or private SSH keys.
* Use environment variables for secrets management.
* Restrict Docker daemon access to trusted users.
* Keep Docker and system packages updated regularly.

---

# Contributing

Contributions are welcome.

## Workflow

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature/my-feature
```

3. Commit changes

```bash
git commit -m "Add new feature"
```

4. Push changes

```bash
git push origin feature/my-feature
```

5. Open a Pull Request

---

## License

This project is licensed under the MIT License.

See the [LICENSE](LICENSE) file for more information.
