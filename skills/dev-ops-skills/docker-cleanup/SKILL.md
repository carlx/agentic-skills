---
name: docker-cleanup
description: Remove unused Docker containers, images, and volumes to free up disk space.
metadata:
  version: "1.1"
---

# Docker Cleanup

Free up disk space by removing unused Docker resources.

## Steps

1. Run `docker system prune -f` to remove stopped containers, dangling images, and unused networks.
2. Run `docker volume prune -f` to remove unused volumes.
3. Report how much space was freed.
