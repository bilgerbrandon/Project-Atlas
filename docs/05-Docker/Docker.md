# Docker Installation

## Purpose

Install Docker CE from the official Docker repository on Ubuntu Server.

## Verification Commands

```bash
docker --version
docker compose version
sudo systemctl is-enabled docker
sudo systemctl is-active docker
sudo docker run --rm hello-world
```

## Lessons Learned

- Remove conflicting legacy packages before installing Docker CE
- Verify both the Docker engine and Compose plugin
- Use restart policies for persistent services
- Keep deployment definitions in version control
- Never commit secrets
