# Security Policy

## Scope

Project Atlas is a homelab and learning environment. This repository intentionally excludes live credentials, secrets, private keys, tokens, public IP addresses, and sensitive network details.

## Reporting a Problem

Do not open a public issue containing:

- Passwords
- API tokens
- Private keys
- Exact public IP addresses
- Personally identifying information
- Unredacted security-sensitive screenshots

Use a private communication channel when one is available.

## Repository Safety Rules

- Never commit `.env` files containing secrets
- Use `.env.example` with placeholder values
- Review screenshots before every commit
- Do not publish Proxmox tickets, Tailscale keys, session cookies, or SSH keys
- Keep management interfaces behind trusted networks or VPN access
- Do not expose Proxmox directly to the internet
- Treat RAID as availability, not backup
