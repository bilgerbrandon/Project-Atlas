# Project Atlas Roadmap

This roadmap keeps the build organized into clear, reviewable phases. A phase is considered complete only when the implementation, verification, screenshots, lessons learned, and GitHub documentation are finished.

## Phase 1 — Planning

**Goal:** Define the architecture, naming standards, documentation conventions, and project scope.

- [x] Define Project Atlas identity
- [x] Establish phased workflow
- [x] Create repository structure
- [x] Create documentation template
- [ ] Finalize IP addressing plan
- [ ] Create final architecture diagram
- [ ] Define backup and recovery objectives

## Phase 2 — Hardware

**Goal:** Assemble and document the physical platform.

- [x] Select primary Proxmox host
- [x] Install system and VM storage
- [x] Acquire managed switch
- [x] Acquire RAID enclosure and drives
- [ ] Complete DeskPi RackMate T2 assembly
- [ ] Mount all mini PCs
- [ ] Install patch panel and cable management
- [ ] Add UPS
- [ ] Label all hardware and cables

## Phase 3 — Networking

**Goal:** Build a documented, manageable, and expandable network.

- [x] Upgrade to Spectrum Gig Internet
- [x] Install TP-Link TL-SG108E switch
- [x] Confirm gigabit connectivity
- [ ] Document physical topology
- [ ] Create management VLAN
- [ ] Create server VLAN
- [ ] Create trusted client VLAN
- [ ] Create IoT VLAN
- [ ] Configure inter-VLAN rules
- [ ] Document DNS and DHCP assignments

## Phase 4 — Proxmox

**Goal:** Establish the virtualization platform.

- [x] Install Proxmox VE
- [x] Configure system storage
- [x] Configure 2 TB LVM-Thin VM storage
- [x] Create Ubuntu Docker VM
- [x] Confirm VM networking
- [x] Configure remote administration
- [ ] Apply final host naming convention
- [ ] Configure scheduled backups
- [ ] Add second Proxmox node
- [ ] Add third Proxmox node
- [ ] Evaluate cluster and quorum design

## Phase 5 — Docker Platform

**Goal:** Create a stable container-management foundation.

- [x] Install Docker CE
- [x] Verify Docker service
- [x] Deploy Portainer
- [x] Deploy Homepage
- [x] Deploy Dozzle
- [x] Configure Tailscale
- [x] Configure VS Code Remote SSH
- [ ] Standardize Docker Compose layout
- [ ] Configure environment files and secrets
- [ ] Add container health checks
- [ ] Configure automated container backups

## Phase 6 — Storage

**Goal:** Provide resilient bulk storage for media, backups, and project data.

- [x] Diagnose Mediasonic ProRAID enclosure
- [x] Initialize four-drive RAID 5 array
- [x] Verify 10.92 TiB in Proxmox
- [x] Create `media` directory storage
- [x] Mount storage at `/mnt/pve/media`
- [ ] Create media and download directory structure
- [ ] Define permissions and ownership model
- [ ] Present storage safely to the Docker VM
- [ ] Configure SMART and enclosure monitoring
- [ ] Test drive-failure and rebuild procedures
- [ ] Define external backup strategy

## Phase 7 — Media Stack

**Goal:** Deploy a maintainable media platform following TRaSH Guides principles.

- [ ] Jellyfin
- [ ] Sonarr
- [ ] Radarr
- [ ] Prowlarr
- [ ] Bazarr
- [ ] qBittorrent
- [ ] Recyclarr
- [ ] Consistent paths and hardlinks
- [ ] Hardware transcoding
- [ ] Remote access policy
- [ ] Backup and restore test

## Phase 8 — Monitoring and Security

**Goal:** Add visibility, alerting, and security controls.

- [ ] Wazuh
- [ ] Uptime monitoring
- [ ] Metrics collection
- [ ] Grafana dashboards
- [ ] Centralized logging
- [ ] Host firewall review
- [ ] MFA review
- [ ] Vulnerability scanning
- [ ] Alerting workflow

## Phase 9 — Automation

**Goal:** Reduce manual work and improve consistency.

- [ ] Infrastructure configuration scripts
- [ ] Docker deployment scripts
- [ ] Backup automation
- [ ] Update workflow
- [ ] Health checks
- [ ] Documentation checks
- [ ] GitHub Actions linting

## Phase 10 — Additive Manufacturing

**Goal:** Use the Bambu Lab P1S to support the physical homelab.

- [ ] Printer installation
- [ ] AMS setup
- [ ] Filament storage and drying plan
- [ ] Rack brackets and accessories
- [ ] Cable-management parts
- [ ] Print settings documentation
- [ ] Final rack photos

## Phase 11 — Portfolio Release

**Goal:** Publish a polished, employer-ready project.

- [ ] Replace all placeholder screenshots
- [ ] Finalize diagrams
- [ ] Verify every internal link
- [ ] Remove sensitive information
- [ ] Add project demo video
- [ ] Create release tag
- [ ] Publish LinkedIn project summary
