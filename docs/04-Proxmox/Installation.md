# Proxmox Installation

## Purpose

Install and verify the Proxmox VE hypervisor on the primary host.

## High-Level Procedure

1. Download the Proxmox VE ISO
2. Create a bootable installer
3. Boot the primary host from USB
4. Install Proxmox to the 256 GB system NVMe
5. Configure the management interface
6. Sign in to the web interface
7. Apply updates
8. Confirm storage and networking
9. Create the Ubuntu Docker VM

## Verification

```bash
pveversion
hostnamectl
ip addr
pvesm status
```

## Evidence to Capture

- Proxmox login page
- Node summary
- Storage list
- Network interface configuration
- Successful update task
