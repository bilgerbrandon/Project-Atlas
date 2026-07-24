# Network Diagram

```mermaid
flowchart LR
    Internet --> Router
    Router --> ManagedSwitch
    ManagedSwitch --> Proxmox
    ManagedSwitch --> AdminMac
    ManagedSwitch -. Future .-> Node2
    ManagedSwitch -. Future .-> Node3
    AdminMac -. Tailscale .-> DockerVM
    Proxmox --> DockerVM
```
