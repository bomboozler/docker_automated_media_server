# Automated Docker Based Media Server 

This repository contains a fully automated setup for a media server using Docker and Docker Compose. With single docker compose file it provisions a range of applications to create a robust media ecosystem. With a single command, you can deploy the entire environment on a compatible server and have your own automated media server!.

## Features
- **Fully Automated**: Using Docker and Docker Compose, this setup automates the deployment and management of various media applications.
- **Easy to Use**: With a single `docker-compose.yml` file, you can bring up the entire stack with minimal effort.

## Components
The following Docker containers are provisioned as part of the media server setup:

### 1. **Immich Server**
   - **Image**: `ghcr.io/immich-app/immich-server:release`
   - **Description**: A self-hosted media server designed for managing and sharing photos and videos.

### 2. **Redis**
   - **Image**: `redis:6.2-alpine`
   - **Description**: An in-memory data structure store, used as a database, cache, and message broker, often utilized by other services for session management.

### 3. **PostgreSQL**
   - **Image**: `tensorchord/pgvecto-rs:pg14-v0.2.0`
   - **Description**: A relational database management system that stores structured data for the media server.

### 4. **Immich Machine Learning**
   - **Image**: `ghcr.io/immich-app/immich-machine-learning:release`
   - **Description**: Handles machine learning tasks for the Immich application.

### 5. **Autoheal**
   - **Image**: `willfarrell/autoheal:latest`
   - **Description**: Automatically restarts unhealthy containers to ensure high availability.

### 6. **SABnzbd**
   - **Image**: `lscr.io/linuxserver/sabnzbd:latest`
   - **Description**: A web-based automated Usenet downloader, allowing you to manage downloads from Usenet.

### 7. **Transmission**
   - **Image**: `linuxserver/transmission:latest`
   - **Description**: A lightweight BitTorrent client for downloading torrents.

### 8. **Bazarr**
   - **Image**: `linuxserver/bazarr:latest`
   - **Description**: A companion application to manage subtitles for your media library.

### 9. **Dozzle**
   - **Image**: `amir20/dozzle:latest`
   - **Description**: A simple, lightweight log viewer for Docker containers, accessible via a web interface.

### 10. **LibreSpeed**
   - **Image**: `linuxserver/librespeed:latest`
   - **Description**: A self-hosted speed test for checking internet speeds without relying on third-party services.

### 11. **Jellyfin**
   - **Image**: `linuxserver/jellyfin:latest`
   - **Description**: A free and open-source media server for streaming your movies, TV shows, music, and more.

### 12. **Radarr**
   - **Image**: `ghcr.io/hotio/radarr:latest`
   - **Description**: An automatic movie downloader that manages and organizes your movie collection.

### 13. **Sonarr**
   - **Image**: `linuxserver/sonarr:latest`
   - **Description**: An automatic TV series downloader, managing your TV shows and organizing them.

### 14. **Portainer**
   - **Image**: `portainer/portainer-ee:latest`
   - **Description**: A lightweight management UI for Docker, allowing you to easily manage your containers.

### 15. **Lidarr**
   - **Image**: `hotio/lidarr:release`
   - **Description**: An automatic music downloader, managing your music collection and keeping it up to date.

### 16. **Prowlarr**
   - **Image**: `ghcr.io/linuxserver/prowlarr:latest`
   - **Description**: A companion application for managing indexers for your downloaders (Sonarr, Radarr, etc.).

### 17. **Jellyseerr**
   - **Image**: `fallenbagel/jellyseerr:latest`
   - **Description**: A request management application that integrates with Jellyfin to manage user requests.

### 18. **Pi-hole**
   - **Image**: `pihole/pihole:latest`
   - **Description**: A network-wide ad blocker that acts as a DNS sinkhole.

### 19. **FlareSolverr**
   - **Image**: `ghcr.io/flaresolverr/flaresolverr:latest`
   - **Description**: A proxy solution for bypassing captchas on various sites when downloading content.

### 20. **Watchtower**
   - **Image**: `containrrr/watchtower:latest`
   - **Description**: Automatically updates your running Docker containers whenever a new image is available.

## Getting Started

### Prerequisites
- Make sure you have Docker and Docker Compose installed on your server.

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/bomboozler/docker_automated_media_server
   cd docker_automated_media_server
   ```
2. Run the following docker compose command:
   ```
   docker compose up -d
   ```
### Updating all docker images
1. Stop the docker compose stack:
   ```
   docker compose down
   ```
2. Pull new images and get it back and running:
   ```
   docker compose pull && docker compose up -d
   ```
