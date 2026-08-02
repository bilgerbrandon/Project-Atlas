# Phase 03 — Network

## Purpose

Create a stable, documented network that supports virtualization, remote administration, media services, and future security controls.

## Current State

- Spectrum Gig Internet
- Approximately 896 Mbps download
- Approximately 39 Mbps upload
- Approximately 18 ms latency
- TP-Link TL-SG108E managed switch
- Tailscale remote access
- Proxmox and Docker VM connected over gigabit Ethernet

## Planned Logical Segmentation

| VLAN | Purpose | Status |
|---|---|---|
| Management | Proxmox, switches, infrastructure | Planned |
| Servers | VMs, containers, internal services | Planned |
| Trusted | Personal computers and phones | Planned |
| IoT | Smart-home and less-trusted devices | Planned |
| Guest | Internet-only guest access | Planned |

## Remote Access

Tailscale currently provides encrypted remote access to the Ubuntu Docker VM and administrative devices without exposing management interfaces directly to the public internet.

## Required Documentation

- Physical topology
- Logical VLAN topology
- IP plan
- DHCP reservations
- DNS names
- Firewall rules
- Remote access policy
- Recovery steps if network access is lost

---

[← Return to Project Atlas](../../README.md) · [Documentation index](../README.md)

