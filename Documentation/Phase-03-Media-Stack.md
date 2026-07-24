# Phase 3 - Media Platform Deployment

## Objective

Deploy the core self-hosted media platform using Docker Compose on the Ubuntu Docker VM.

This phase establishes the foundation for an automated media environment that will later integrate download automation, indexing, and media streaming.

---

# Environment

## Host Infrastructure

- Proxmox VE
- Ubuntu Server VM
- Docker Engine
- Docker Compose

---

# Services Deployed

| Service | Purpose | Port |
|----------|---------|------|
| Homepage | Dashboard | Configured |
| Portainer | Docker Management | 9443 |
| Dozzle | Container Logs | 8080 |
| Jellyfin | Media Server | 8096 |
| Prowlarr | Index Manager | 9696 |
| Sonarr | TV Management | 8989 |
| Radarr | Movie Management | 7878 |

---

# Storage Layout

```
/media
├── data
│   ├── movies
│   ├── tv
│   └── torrents
│       ├── complete
│       └── incomplete
│
└── docker
    ├── jellyfin
    ├── prowlarr
    ├── sonarr
    └── radarr
```

---

# Docker Architecture

Each application runs in its own isolated Docker container while sharing persistent storage through bind mounts.

Persistent application configuration is stored in:

```
/media/docker
```

Media libraries are stored in:

```
/media/data
```

This separation allows containers to be recreated without losing configuration or media.

---

# Current Service Status

## Operational

- ✅ Portainer
- ✅ Homepage
- ✅ Dozzle
- ✅ Jellyfin
- ✅ Prowlarr
- ✅ Sonarr
- ✅ Radarr

---

# Jellyfin

Jellyfin has been successfully deployed.

Current status:

- Administrative account configured
- Accessible through browser
- Awaiting media library configuration
- Ready to consume Movies and TV folders after automation pipeline is completed

---

# Sonarr

Configured with:

- Persistent configuration
- TV Library
- Shared Downloads directory

Volume Mapping

```
/media/docker/sonarr   -> /config
/media/data/tv         -> /tv
/media/data/torrents   -> /downloads
```

---

# Radarr

Configured with:

- Persistent configuration
- Movie Library
- Shared Downloads directory

Volume Mapping

```
/media/docker/radarr   -> /config
/media/data/movies     -> /movies
/media/data/torrents   -> /downloads
```

---

# Prowlarr

Successfully deployed.

Authentication configured.

Ready to connect to:

- Sonarr
- Radarr

---

# Verification

Verified:

- Docker containers running
- Persistent storage functioning
- VirtioFS mount operational
- Correct volume mappings
- Web interfaces accessible
- Authentication configured
- Jellyfin operational

---

# Lessons Learned

- Docker Compose provides reproducible infrastructure.
- Separating container configuration from application data greatly simplifies recovery.
- Using a shared downloads directory enables efficient hardlinking for the Servarr ecosystem.
- Planning the storage layout before downloading media prevents future migration issues.

---

# Remaining Tasks

- Install qBittorrent
- Connect qBittorrent to Sonarr
- Connect qBittorrent to Radarr
- Connect Prowlarr applications
- Configure Indexers
- Configure Jellyfin libraries
- Test complete automated workflow
- Deploy Bazarr
- Deploy Recyclarr

---

# Architecture

```
                    Internet
                         │
                         ▼
                  +-------------+
                  |  Prowlarr   |
                  +------+------+
                         │
              +----------+----------+
              │                     │
              ▼                     ▼
        +-----------+         +-----------+
        |  Sonarr   |         |  Radarr   |
        +-----+-----+         +-----+-----+
              │                     │
              +----------+----------+
                         │
                         ▼
                 qBittorrent
                    (Next)
                         │
                         ▼
                  /media/data
                  ├── movies
                  ├── tv
                  └── torrents
                         │
                         ▼
                    Jellyfin
```

---

# Phase Outcome

Successfully deployed the core media platform using Docker Compose with persistent storage, isolated services, and an enterprise-style directory structure. The environment is now ready for download automation and media library integration.