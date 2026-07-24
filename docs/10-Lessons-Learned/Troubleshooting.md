# Troubleshooting Log

## RAID Enclosure Would Not Stay Online

**Symptoms:** Beeping, flashing red LEDs, drives powering down, 0-byte USB device.

**Diagnosis:** Hardware interface detected, but no usable logical disk was exported.

**Root cause:** RAID mode had not been committed with the hidden confirmation button.

**Resolution:** Confirmed RAID 5, restarted the enclosure, verified 10.92 TiB in Proxmox.

## Wrong Shell Context

**Symptoms:** Disk command produced a warning that partitions were in use.

**Diagnosis:** Prompt showed `brandon@ubuntu-docker`, not `root@datto`.

**Risk:** The VM's virtual disk could have been damaged.

**Resolution:** Cancelled the operation and returned to the Proxmox host.

## Documentation Lesson

Troubleshooting failures are not embarrassing repository content. When written clearly, they demonstrate careful diagnosis, risk recognition, and recovery.
