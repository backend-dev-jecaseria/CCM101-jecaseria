# Laboratory 10 - Enterprise Cloud Architect

## Mission Overview
I designed, deployed, secured, automated, and documented a private cloud stack for CloudNova Technologies with no step-by-step guide. The stack is a Ghost website (web tier) and a MySQL 8.0 database (database tier). Both run in Docker containers on Ubuntu Server inside VirtualBox. The database and site content use persistent volumes. UFW blocks everything except SSH and the web port. A Bash script backs up the database every night at 2:00 AM with cron.

## Objectives
- Conceptualize and diagram a custom enterprise cloud infrastructure
- Provision a local Ubuntu Server VM and reach it from the host browser
- Install Docker and Docker Compose and write a multi-tier docker-compose.yml
- Use persistent volumes so data survives a reboot
- Secure the server with UFW using a default deny policy
- Automate a database backup with a Bash script and cron
- Document everything in a Markdown operational manual and defend the setup live

## Repository Contents
| File | Description |
|------|-------------|
| architecture-diagram.png | Network and architecture diagram |
| docker-compose.yml | Ghost + MySQL stack with persistent volumes |
| automation-script.sh | Daily database backup script |
| operational-manual.md | How to deploy, secure, and maintain the stack |
| final-reflection.md | Reflection from Mission 1 to Mission 10 |

## Commands Executed
~~~
sudo apt update && sudo apt upgrade -y
sudo timedatectl set-timezone Asia/Manila
sudo apt install -y docker.io docker-compose-v2
sudo systemctl enable --now docker
sudo usermod -aG docker $USER
docker run hello-world
mkdir ~/cloudnova && cd ~/cloudnova
nano .env
chmod 600 .env
docker compose config
docker compose pull
docker compose up -d
docker compose ps
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw enable
sudo ufw status verbose
sudo ss -tulpn
nano automation-script.sh
chmod +x automation-script.sh
./automation-script.sh
ls -lh ~/backups
crontab -e
crontab -l
sudo reboot
docker ps
~~~

## Skills Learned
- Planning and diagramming a network and container architecture
- Writing a docker-compose.yml with linked containers, a healthcheck, and persistent volumes
- Keeping passwords out of the compose file with a protected .env file
- Hardening a server with UFW and keeping the database port closed
- Writing a backup script, scheduling it with cron, and testing a restore
- Troubleshooting networking, resource, and firewall problems
- Documenting an operational manual in Markdown and using Git/GitHub
