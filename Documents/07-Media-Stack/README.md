# Media Stack

## Overview

The Atlas Media Stack provides automated media management using Docker containers running on an Ubuntu Server virtual machine hosted by Proxmox.

## Services

| Service | Purpose |
|----------|---------|
| Jellyfin | Media server |
| Sonarr | TV series management |
| Radarr | Movie management |
| Prowlarr | Indexer management |
| qBittorrent | Download client |
| FlareSolverr | Cloudflare proxy for supported indexers |

## Storage Layout

```
/media/data
├── media
│   ├── movies
│   └── tv
│
├── torrents
│   ├── movies
│   ├── tv
│   └── incomplete
│
└── docker
    ├── sonarr
    ├── radarr
    ├── prowlarr
    └── qbittorrent
```

## Architecture

```
Sonarr ─────┐
            │
Radarr ─────┼────► qBittorrent
            │
Prowlarr ───┘
                 │
                 ▼
           /media/data
                 │
                 ▼
             Jellyfin
```