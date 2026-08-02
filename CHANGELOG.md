# Changelog

All notable changes to Project Atlas are documented here.

## [Unreleased]

### Added

- Branded Project Atlas SVG banner
- Employer-focused README landing page
- Documentation index and phase navigation
- Contribution guide and security policy
- MkDocs configuration
- GitHub Pages publishing workflow
- Portfolio release checklist

### Changed

- Repository organization now follows a phased case-study format
- Photos are stored with the phase where they are used
- Project journal uses a consistent milestone format

## [0.2.0] — 2026-07-24

### Added

- 12 TB RAID 5 array
- Proxmox directory storage named `media`
- Mount point `/mnt/pve/media`

### Fixed

- Mediasonic enclosure initialization failure caused by an unconfirmed RAID mode

## [0.1.0]

### Added

- Initial Proxmox host
- Ubuntu Docker VM
- Docker CE
- Portainer
- Homepage
- Dozzle
- Tailscale remote access

## Sprint 2 – Media Platform

### Added

- Jellyfin media server
- Prowlarr index management
- Sonarr TV automation
- Radarr movie automation
- qBittorrent download client
- FlareSolverr support

### Configured

- Shared `/media/data` storage
- Docker networking
- Unified media library structure
- Jellyfin media libraries
- Sonarr and Radarr root folders
- qBittorrent integration

### Fixed

- VirtIOFS storage mapping
- Proxmox storage mount
- Jellyfin volume mapping
- Container path standardization