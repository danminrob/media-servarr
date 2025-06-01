# Media Servarr Stack!

forked from Wh1rr/ultimate-jellyfin-stack

## Overview

This Stack includes the following services:

- **Jellyfin:** Media server for streaming movies and TV shows.
- **Radarr:** Movie management and automation.
- **Sonarr:** TV show management and automation.
- **Readarr:** Used to grab books and audiobooks.
- **Lidarr:** Used to grab music.
- **Kapowarr** Used to grab comics.
- **Prowlarr:** Indexer manager for Radarr and Sonarr.
- **Jellyseerr:** Request management and monitoring for Jellyfin.
- **Gluetun:** VPN container with WireGuard support for secure browsing. Disabled by default.
- **Qbittorrent:** BitTorrent client with VPN support.
- **Tdarr:** Pre-transcodes your media to decrease file sizes
- **Bazarr:** Subtitle management for movies and TV shows.
- **Autobrr:** Used to grab torrents immediately as they are released. Disabled by default.
- **Flaresolverr:** Used as a proxy server to bypass Cloudflare and DDoS-GUARD protection.
- **Dozzle:** Used to view the logs of any container.
- **Wizarr:** Used to create links that can be sent to users so they can be invited to your media server. Disabled by default.
- **Homarr:** Used as a dashboard for docker containers with integrations for the *arr, torrent, and Jellyfin apps.
- **Decluttarr:** Used to maintain/clean your *arr app queues and downloads.
- **Jellystat:** Used to monitor the usage of each user or content on your jellyfin server. Disabled by default.
- **tinyMediaManager** Media art scrapper.

## Dependencies

1. Linux
2. Docker / Docker Compose
3. OPTIONAL but HIGHLY RECOMMENDED: Portainer - Docker GUI

## How to Use - Using portainer
1. Create a new stack using the Repository build method
2. Add this link `https://github.com/danminrob/media-servarr/blob/main/docker-compose.yml` as repository URL
3. Add your environment variables using the below examples.

## Environment variables in Portainer
- PUID=1000
- PGID=1000
- TZ=America/Mexico_City
- BASE_PATH=/mnt/LinuxD/media_servarr/config/ (Local directory where the configuration of the diferent services will be saved)
- MEDIA_SHARE=/mnt/LinuxD/media_servarr/content/ (Local directory where the media downloaded by the diferent services will be saved)
- QBIT_USER=admin
- QBIT_PASS=Jhrzx$LFY5s# (Access the qbittorrent container logs to obtain the temporaly password, use it to acces the WebUI http://localhost:1337/ , go to Options -> WebUI and set your own Password)
- RADARR_KEY= (Access radarr in http://localhost:7878 , go to Settings -> General -> API Key)
- SONARR_KEY= (Access radarr in http://localhost:8989 , go to Settings -> General -> API Key)
- LIDARR_KEY= (Access radarr in http://localhost:8686 , go to Settings -> General -> API Key)
- READARR_KEY= (Access radarr in http://localhost:8787 , go to Settings -> General -> API Key)
  
## What's the use of these apps
1. Prowlarr manages the indexes(Torrent providers) for *some* starr apps (radarr and sonarr)
2. The following starr apps make use of the download client (qBittorent) to download their respective content type:
   1. Radarr - Movies
   2. Sonarr - TV Shows
   3. Lidarr - Music
   4. Readarr - Books
   5. Kapowarr - Comics
3. Jellyseer is a platform which combines the request system in radarr and sonarr to make a nice UI/UX to find and auto download the content.

## Recommendations

1. Install portainer to manage and monitor containers
2. There's A LOT to be configured at each app, read carefully
3. Backup your "BASE_PATH" contents once you are done

## Ports directory
- **Jellyfin** http://localhost:8096
- **Jellyseer** http://localhost:5055
- **qBittorent** http://localhost:1337
- **Radarr** http://localhost:7878
- **Sonarr** http://localhost:8989
- **Lidarr** http://localhost:8686
- **Readarr** http://localhost:8787
- **Homarr** http://localhost:7575
- **tinyMediaManager** http://localhost:4000
