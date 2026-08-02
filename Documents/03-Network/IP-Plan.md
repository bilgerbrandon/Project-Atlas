# IP Address Plan

> Replace placeholders after the final VLAN and subnet design is approved.

| Device | Hostname | Network | Addressing | Notes |
|---|---|---|---|---|
| Proxmox primary | `datto` | Management | Static / reservation | Current address should not be published publicly |
| Ubuntu Docker VM | `ubuntu-docker` | Servers | Static / reservation | Hosts Docker services |
| Managed switch | TBD | Management | Static / reservation | TP-Link TL-SG108E |
| Secondary node | TBD | Management | Static / reservation | OptiPlex 7070 |
| Lab node | TBD | Management | Static / reservation | OptiPlex 7040 |

## Rules

- Infrastructure receives stable addresses
- DHCP reservations are preferred where appropriate
- Public documentation should use examples or redacted values
- Hostnames must remain consistent across DNS, Proxmox, SSH, and documentation
