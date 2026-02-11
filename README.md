# Docker Storage Labs (Bind Mounts vs Volumes)

This repo documents hands-on Docker storage practice on AWS EC2 (Ubuntu).

## What I practiced
- Bind mounts: host folder ↔ container folder
- Bind mount failure test: deleting host folder causes data loss
- Docker volumes: Docker-managed persistent storage
- Volume persistence test: delete container, data still exists

## Labs
### Lab 1 — Bind Mount (Basic)
- Create host folder `~/bind-lab`
- Mount to container `/data`
- Create a file in `/data`
- Verify the file appears on the host

### Lab 2 — Bind Mount (Failure Scenario)
- Delete the host folder
- Re-run container
- Observe `/data` becomes empty (data loss)

### Lab 3 — Volume Persistence
- Create volume `vol-lab`
- Write `/data/v.txt`
- Remove container
- Re-run container with same volume and verify file remains

## Environment
- AWS EC2 (Ubuntu)
- Docker Engine

## Author
SanthoshK12

