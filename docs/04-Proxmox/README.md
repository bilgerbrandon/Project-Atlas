# Phase 04 — Proxmox

## Purpose

Provide the virtualization foundation for Project Atlas.

## Host Summary

- Hostname: `datto`
- Platform: Datto / Dell OptiPlex 7000 Micro
- CPU: Intel Core i5-12500T
- Memory: 16 GB DDR5
- System disk: 256 GB KIOXIA NVMe
- VM storage: 2 TB SK hynix PC801 NVMe
- Bulk storage: 10.92 TiB hardware RAID 5

## Storage Roles

| Storage | Type | Role |
|---|---|---|
| `local` | Directory | ISOs, templates, backups, snippets |
| `local-lvm` | LVM-Thin | Default VM and container disks |
| `vg_vmdata` | LVM-Thin | High-capacity VM disk storage |
| `media` | ext4 Directory | Bulk media, backups, and application data |

## Current Workloads

- Ubuntu Docker VM
- Portainer
- Homepage
- Dozzle
- Tailscale

## Verification

```bash
pveversion
lsblk
pvesm status
qm list
```

## Safety Rule

Before running any disk command, verify:

```bash
hostname
lsblk -o NAME,SIZE,MODEL,SERIAL,FSTYPE,MOUNTPOINTS
```

The expected Proxmox shell prompt is:

```text
root@datto:~#
```

Do not partition or format disks while connected to the Ubuntu Docker VM.

---

[← Return to Project Atlas](../../README.md) · [Documentation index](../README.md)

