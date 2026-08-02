# Phase 01 — Planning

## Purpose

Define the goals, scope, architecture, naming standards, documentation workflow, and success criteria for Project Atlas.

## Project Goals

- Build practical systems-administration experience
- Create a reliable home virtualization platform
- Learn networking, Linux, storage, containers, monitoring, and security
- Build a portfolio that demonstrates technical and documentation skills
- Produce instructions that another learner could follow

## Design Principles

- Prefer simple, understandable systems
- Document before moving to the next milestone
- Verify every change
- Avoid unnecessary public exposure
- Maintain clear separation between infrastructure, applications, and data
- Use reproducible configurations wherever possible

## Naming Standard

| Asset | Name |
|---|---|
| Primary Proxmox host | `datto` |
| Ubuntu Docker VM | `ubuntu-docker` |
| Docker management | `portainer` |
| Service dashboard | `homepage` |
| Log viewer | `dozzle` |
| Bulk storage | `media` |
| Project repository | `Project-Atlas` |

## Success Criteria

Project Atlas is successful when:

- Core infrastructure is stable and documented
- Services survive restarts
- Backups can be restored
- Storage and permissions are understood
- Monitoring provides useful alerts
- The repository can be reviewed quickly by an employer
- Another person could recreate the main architecture from the documentation

## Next Steps

Finalize network addressing, rack design, and backup objectives.

---

[← Return to Project Atlas](../../README.md) · [Documentation index](../README.md)

