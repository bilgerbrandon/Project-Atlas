# VLAN Plan

## Objective

Separate infrastructure, servers, trusted clients, IoT devices, and guests to reduce unnecessary access between device groups.

## Proposed Policy

- Trusted devices may access approved server services
- Management interfaces are accessible only from trusted administrative devices
- IoT devices cannot initiate connections to management systems
- Guest devices receive internet access only
- Public-facing services should use a controlled reverse proxy or VPN strategy
- Proxmox management should never be exposed directly to the internet

## Validation

- Confirm VLAN tagging on the switch
- Confirm DHCP scope for each VLAN
- Confirm intended cross-VLAN access
- Confirm denied paths are actually blocked
- Document an emergency recovery port or procedure
