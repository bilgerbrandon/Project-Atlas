# Phase 06 — Storage

## Purpose

Provide resilient bulk storage for media, downloads, backups, and future services.

## Hardware

- Mediasonic ProRAID Smart Family HFR2-SU3S2
- Four 4 TB SATA hard drives
- RAID level: RAID 5
- Raw marketed capacity: 16 TB
- Usable capacity reported by Linux: 10.92 TiB
- Proxmox storage ID: `media`
- Mount path: `/mnt/pve/media`

## Architecture

```mermaid
flowchart LR
    D1[4 TB HDD] --> RAID[Mediasonic Hardware RAID 5]
    D2[4 TB HDD] --> RAID
    D3[4 TB HDD] --> RAID
    D4[4 TB HDD] --> RAID
    RAID --> USB[USB Storage Interface]
    USB --> PVE[Proxmox Host]
    PVE --> EXT4[ext4 Filesystem]
    EXT4 --> MEDIA[/mnt/pve/media]
    MEDIA -. Planned .-> VM[Ubuntu Docker VM]
```

## Troubleshooting Case Study

### Symptoms

- Fans and disks powered on
- The enclosure beeped
- Drive LEDs changed from blue to flashing red
- Drives powered down while the enclosure remained on
- USB identified an ASMedia controller
- Linux reported a 0-byte device
- eSATA showed the SATA link down

### Investigation

The drives were erased and retested, which ruled out stale filesystem data as the primary cause. The enclosure electronics were responsive, but the array had not been fully committed.

### Root Cause

The RAID 5 selection required confirmation through a hidden hardware button. The selected mode was visible on the front panel but had not been applied.

### Resolution

1. Installed all four drives
2. Selected RAID 5 using the front MODE control
3. Located the hidden confirmation button
4. Confirmed the RAID mode
5. Allowed the enclosure to power down
6. Restarted the enclosure
7. Verified the drives remained online
8. Confirmed `/dev/sda` appeared as `10.92 TiB`
9. Initialized the disk with GPT in Proxmox
10. Created ext4 directory storage named `media`

## Verification

```bash
lsblk -o NAME,SIZE,MODEL,FSTYPE,MOUNTPOINTS
fdisk -l /dev/sda
findmnt /mnt/pve/media
df -hT /mnt/pve/media
pvesm status
```

Expected result:

```text
/dev/sda1 mounted at /mnt/pve/media
approximately 10.9 TiB total capacity
Proxmox storage media enabled
```

## Safety and Recovery

- RAID 5 tolerates one drive failure
- RAID is not a backup
- Avoid disconnecting power during rebuild
- Replace failed drives with equal or larger capacity
- Document the enclosure LED and alarm behavior
- Maintain another copy of irreplaceable files

## Next Steps

- Create the media folder structure
- Define UID, GID, ownership, and permissions
- Decide how to present storage to the Docker VM
- Test sustained reads and writes
- Add health monitoring
- Create an external backup plan

---

[← Return to Project Atlas](../../README.md) · [Documentation index](../README.md)

