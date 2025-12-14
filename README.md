# Multimedia (Docker Compose)

Small home-media stack using linuxserver.io containers (qBittorrent, Sonarr, Radarr, Prowlarr, Jackett, Jellyfin, Plex).

## Quick start

1) Copy the env template and adjust values:
    - Copy `.env.example` to `.env`
    - Set `ARRPATH` (keep the trailing `/`)
    - Set `PUID`/`PGID` to match your Linux/WSL user (`id -u`, `id -g`)

2) Start the stack:
    - `docker compose up -d`

## Updating images

- `docker compose pull`
- `docker compose up -d`

(Optional cleanup)

- `docker image prune -f`

## Services / URLs

- Homepage (dashboard): <http://localhost:3000>
- qBittorrent: <http://localhost:8080>
- Prowlarr: <http://localhost:9696>
- Jackett: <http://localhost:9117>
- Sonarr: <http://localhost:8989>
- Radarr: <http://localhost:7878>
- Jellyfin: <http://localhost:8096>
- Plex (host network): <http://localhost:32400/web>

## Notes for WSL

If containers start with "default" config and only work after a restart, it's almost always volume permission/ownership.
Make sure the host folders under `ARRPATH` are writable by `PUID`/`PGID`.
