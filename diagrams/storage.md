# Storage Diagram

```mermaid
flowchart LR
    A[4 TB] --> R[RAID 5]
    B[4 TB] --> R
    C[4 TB] --> R
    D[4 TB] --> R
    R --> S[/dev/sda]
    S --> P[GPT Partition]
    P --> E[ext4]
    E --> M[/mnt/pve/media]
    M -. Planned .-> DockerVM[Ubuntu Docker VM]
```
