# Media Storage Layout

## Proposed Directory Structure

```text
/mnt/pve/media/
├── data/
│   ├── media/
│   │   ├── movies/
│   │   ├── tv/
│   │   ├── music/
│   │   └── books/
│   ├── torrents/
│   │   ├── movies/
│   │   ├── tv/
│   │   └── incomplete/
│   └── usenet/
│       ├── complete/
│       └── incomplete/
├── backups/
│   ├── proxmox/
│   ├── docker/
│   └── configs/
├── iso/
└── project-data/
```

## Design Principle

For a future Sonarr, Radarr, and download-client stack, keep downloads and media under one shared filesystem tree. This supports efficient moves and hardlinks when the storage is presented correctly to the Docker VM.

## Permissions Plan

Before creating application containers, define:

- Service account
- Shared media group
- UID and GID
- Directory ownership
- File and directory modes
- Umask
- Container path mappings

Do not use broad `777` permissions as a permanent solution.
