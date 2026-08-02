# External Storage Recovery

## Summary

After moving the homelab hardware, the external storage enclosure disconnected unexpectedly.

This prevented Proxmox from mounting the storage volume and caused VM startup failures due to missing VirtIOFS directory mappings.

---

# Symptoms

- Proxmox boot delays
- Storage inactive
- VM would not start
- VirtIOFS mapping errors
- Missing docker-media directory

---

# Root Cause

The USB-to-eSATA bridge disconnected during hardware movement.

Because the storage was unavailable, Proxmox could not mount:

/mnt/pve/media

The Docker shared directory therefore appeared missing.

---

# Troubleshooting

Verified:

- lsblk
- blkid
- pvesm status
- storage.cfg
- fstab
- mount status

Confirmed:

- Filesystem healthy
- UUID correct
- Storage recovered
- Docker directory intact

---

# Resolution

Updated fstab.

Verified storage configuration.

Mounted storage.

Confirmed:

- media storage active
- docker-media directory accessible
- VM started successfully

---

# Lessons Learned

- External storage should always use nofail.
- Verify storage before starting dependent VMs.
- Test storage after moving hardware.