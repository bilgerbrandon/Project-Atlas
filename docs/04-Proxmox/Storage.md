# Proxmox Storage

## Current Layout

### System Disk

The 256 GB KIOXIA NVMe contains:

- EFI partition
- Proxmox root
- Swap
- Default LVM-Thin storage

### VM Data Disk

The 2 TB SK hynix PC801 NVMe provides dedicated LVM-Thin storage for virtual-machine disks.

### Bulk RAID Storage

The Mediasonic hardware RAID enclosure appears to Proxmox as one block device:

```text
/dev/sda
10.92 TiB
```

Proxmox directory storage:

```text
Storage ID: media
Mount path: /mnt/pve/media
Filesystem: ext4
```

## Verification

```bash
lsblk -f
df -hT /mnt/pve/media
pvesm status
findmnt /mnt/pve/media
```

## Important Limitation

RAID 5 provides drive-failure tolerance, but it is not a backup. Critical data still requires a separate copy on another device or location.
