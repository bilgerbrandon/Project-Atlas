# Homepage

## Purpose

Provide one central dashboard for Project Atlas services.

## Configuration Files

Expected configuration includes:

- `services.yaml`
- `bookmarks.yaml`
- `docker.yaml`
- `proxmox.yaml`
- Optional Kubernetes placeholders

## Design Goal

The user should not need to memorize IP addresses and port numbers. Homepage becomes the visual entry point for frequently used services.

## Verification

```bash
docker ps --filter name=homepage
docker logs --tail 50 homepage
```
