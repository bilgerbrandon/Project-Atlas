# Phase 05 — Docker Platform

## Purpose

Provide a consistent container runtime and management platform.

## Current Services

| Service | Purpose | Status |
|---|---|---|
| Docker CE | Container runtime | Active |
| Portainer CE | Container management | Active |
| Homepage | Service dashboard | Active |
| Dozzle | Live container logs | Active |
| Tailscale | Private remote access | Active |

## Management Workflow

- SSH from the MacBook Air
- VS Code Remote SSH for file editing
- Portainer for visual management
- Docker CLI for verification and troubleshooting
- GitHub for documentation and configuration history

## Verification

```bash
docker version
systemctl status docker --no-pager
docker ps
docker volume ls
docker network ls
```

## Next Improvements

- Migrate services to Docker Compose
- Standardize stack folders
- Add `.env.example`
- Add health checks
- Document backup and restore
- Separate configuration from bulk media data

---

[← Return to Project Atlas](../../README.md) · [Documentation index](../README.md)

