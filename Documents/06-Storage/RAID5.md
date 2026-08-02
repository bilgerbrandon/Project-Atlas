# RAID 5 Implementation

## Why RAID 5

RAID 5 combines capacity and single-drive fault tolerance. With four 4 TB disks, one drive's equivalent capacity is used for distributed parity.

## Capacity

```text
4 drives × 4 TB = 16 TB marketed raw capacity
RAID 5 usable marketed capacity ≈ 12 TB
Linux-reported usable capacity = 10.92 TiB
```

The difference comes from parity and decimal-versus-binary capacity reporting.

## Operational Notes

- One failed drive can be tolerated
- A second failure before rebuild completes can destroy the array
- Rebuilds stress all remaining drives
- Backups remain mandatory for important data
- The hardware enclosure abstracts individual drives from Proxmox

## Failure Procedure

1. Record which bay reports failure
2. Confirm the alarm and LED state
3. Do not remove multiple drives
4. Replace only the failed drive
5. Use an equal or larger replacement
6. Allow the hardware enclosure to rebuild
7. Avoid unnecessary restarts during rebuild
8. Verify the array returns to healthy status
9. Update the project journal
