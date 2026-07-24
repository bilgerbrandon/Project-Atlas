# Phase 07 — Media Stack

## Status

Planned. Deployment begins after storage presentation and permissions are finalized.

## Goal

Deploy a maintainable media platform using consistent paths and TRaSH Guides-aligned configuration.

## Planned Services

| Service | Role |
|---|---|
| Jellyfin | Media playback |
| Sonarr | TV-series management |
| Radarr | Movie management |
| Prowlarr | Indexer management |
| Bazarr | Subtitle management |
| qBittorrent | Download client |
| Recyclarr | Configuration synchronization |

## Deployment Order

1. Finalize storage paths and permissions
2. Deploy download client
3. Deploy Prowlarr
4. Deploy Sonarr
5. Deploy Radarr
6. Deploy Bazarr
7. Deploy Jellyfin
8. Configure Recyclarr
9. Verify hardlinks and imports
10. Test backup and restore

## Quality Requirements

- No inconsistent container paths
- No unnecessary duplicate copies
- Health checks enabled
- Persistent configuration stored separately from media
- Secrets excluded from Git
- Hardware transcoding documented
- Remote access controlled and intentional

---

[← Return to Project Atlas](../../README.md) · [Documentation index](../README.md)

