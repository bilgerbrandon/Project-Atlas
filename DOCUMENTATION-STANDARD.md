# Documentation Standard

Every milestone guide should use the same structure.

## Required Sections

1. **Purpose** — Why this component exists
2. **Scope** — What the guide includes and excludes
3. **Prerequisites** — Hardware, software, access, and assumptions
4. **Architecture** — How the component fits into Project Atlas
5. **Implementation** — Reproducible steps
6. **Verification** — Commands, screenshots, and expected results
7. **Troubleshooting** — Problems encountered and resolutions
8. **Security Considerations** — Credentials, permissions, network exposure, and updates
9. **Lessons Learned** — Practical knowledge gained
10. **Next Steps** — The next milestone

## Screenshot Naming

Use two-digit numbering and lowercase kebab-case:

```text
01-proxmox-disk-detected.png
02-raid5-storage-created.png
03-storage-summary.png
```

## Command Formatting

Use fenced code blocks and specify the language:

```bash
lsblk
```

Show expected output only when it helps validation.

## Sensitive Information

Before committing:

- Blur or remove public IP addresses
- Remove passwords, tokens, API keys, serial numbers, and private URLs
- Avoid publishing exact home addresses
- Review screenshots for browser tabs and personal account information
- Use example credentials and `.env.example`

## Commit Message Format

Use concise conventional-style messages:

```text
docs(storage): document RAID 5 integration
feat(docker): add Portainer deployment guide
fix(network): correct VLAN addressing table
chore(repo): reorganize Project Atlas structure
```
