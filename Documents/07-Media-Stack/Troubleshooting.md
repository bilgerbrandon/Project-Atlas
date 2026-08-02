# Troubleshooting

## VM Would Not Boot

### Cause

VirtIOFS directory mapping referenced unavailable storage.

### Resolution

- Verified Proxmox storage mount
- Corrected storage configuration
- Restored shared directory
- Verified VirtIOFS mount

---

## Jellyfin Could Not See Media

### Cause

Incorrect Docker volume mapping.

Incorrect:

```
./media/data:/data
```

Correct:

```
/media/data:/data
```

---

## Public Indexers

Some public torrent indexers failed due to Cloudflare protection or unavailable mirrors.

Working examples:

- Nyaa
- YTS

FlareSolverr was deployed for compatible indexers.