# Sample Traefik Docker Compose Setup

This repository contains a simple configuration to get started with [Traefik](https://traefik.io/) as a reverse proxy using Docker Compose.

## Prerequisites

- Docker
- Docker Compose
- Domain with cloudflare
- Cloudflare API Key
- Git
  
## Guide
### How to Request Cloudfare API KEY
First of all i'll asume your domain is setup through cloudflare
To create a CloudFlare API token for your DNS zone go to https://dash.cloudflare.com/profile and follow these steps:
1. Go to API TOKENS
2. Click Create Token
3. Click 'Edit zone DNS' from the templates
   - On zone Resources click your zone (your domain)
   - And Click 'Continue to Summary'
4. Click 'Create Token'
5. Copy/Paste your API KEY to 'CF_DNS_API_TOKEN= on your .env file'
### Install docker docker compose and git 
Asuming you already have the apt repository installed 

```bash
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin git
```

### just git clone the repo and...
```bash
git clone https://github.com/Lilithbtw/traefik-sample.git
```
Using your prefered linux text editor just edit the the following line
- "traefik.http.routers.nginx.rule=Host(`mydomain.com`) || Host(`www.mydomain.com`)"
```bash
nano docker-compose.yml
```
### Setup the file structure
```bash
mkdir src
mkdir letsencrypt
touch letsencrypt/acme.json
```

### Final step
Just copy all your PHP files over to src and then just do and it should be working
```bash
docker compose up -d
```
