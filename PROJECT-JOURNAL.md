# Project Atlas Journal

This journal records meaningful changes, problems, solutions, and decisions. Detailed implementation instructions belong in the phase documentation.

## 2026-07-24 — RAID 5 Storage Online

### Completed

- Located the hidden RAID confirmation button on the Mediasonic enclosure
- Initialized a four-drive RAID 5 array
- Confirmed the enclosure remained powered on
- Verified the new device on the Proxmox host as `/dev/sda`
- Confirmed raw usable capacity of `10.92 TiB`
- Initialized the disk with GPT through the Proxmox interface
- Created ext4 directory storage named `media`
- Mounted the storage at `/mnt/pve/media`
- Confirmed the Proxmox task log reported success

### Problem

The enclosure powered up, spun all drives, beeped, flashed red, and then shut down the drives. USB detection exposed an ASMedia controller but no usable capacity, while eSATA reported no link.

### Root Cause

The RAID mode had been selected but not committed. This hardware revision required a hidden confirmation button to finalize the RAID configuration.

### Resolution

Selected RAID 5, pressed the hidden confirmation control, allowed the enclosure to power down, and restarted it. The array then remained online and appeared as a single disk in Proxmox.

### Lessons Learned

- A selected configuration is not always an applied configuration.
- Hardware revisions may differ from publicly available manuals.
- Always verify the shell prompt before running destructive disk commands.
- Confirm device identity and size before partitioning or formatting.
- Troubleshooting notes are valuable portfolio material when documented clearly.

### Next Milestone

Revamp the GitHub repository and then create the media-storage folder and permissions model.

---

## 2026-07-21 — Managed Switch Arrived

### Completed

- Added TP-Link TL-SG108E Easy Smart Managed Switch
- Confirmed fanless gigabit switching
- Added VLAN capability to the future network roadmap

### Next Milestone

Document the physical topology and create a VLAN plan.

---

## 2026-07-20 — Internet Upgrade

### Completed

- Upgraded to Spectrum Gig Internet
- Recorded approximately 896 Mbps download, 39 Mbps upload, and 18 ms latency

### Lesson Learned

Internet bandwidth is no longer the primary limitation for remote access, downloads, or future media services.

---

## Docker Platform Milestone

### Completed

- Installed Docker CE
- Verified the Docker service
- Deployed Portainer CE
- Deployed Homepage
- Deployed Dozzle
- Configured Tailscale
- Configured SSH access from the MacBook Air
- Verified VS Code Remote SSH

### Next Milestone

Standardize services with Docker Compose and persistent storage.
