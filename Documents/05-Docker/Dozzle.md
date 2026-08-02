# Dozzle

## Purpose

Provide a lightweight web interface for viewing Docker logs in real time.

## Verification

```bash
docker ps --filter name=dozzle
docker logs --tail 50 dozzle
```

## Security Note

Container logs may contain internal paths, hostnames, usernames, or tokens. Dozzle should remain limited to trusted networks or private remote access.
