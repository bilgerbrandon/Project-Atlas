# Virtual Machines

## Ubuntu Docker VM

| Setting | Value |
|---|---|
| Name | `ubuntu-docker` |
| Purpose | Docker application host |
| Disk | 100 GB virtual disk |
| Remote access | SSH and Tailscale |
| Administration | MacBook Air and VS Code Remote SSH |

## Design Intent

The VM separates application workloads from the Proxmox host. Docker should not be installed directly on the hypervisor.

## Future Improvements

- Document CPU and memory allocation
- Add QEMU guest agent
- Configure backup job
- Test restore
- Present RAID storage using a deliberate and documented method
- Add service-level health checks
