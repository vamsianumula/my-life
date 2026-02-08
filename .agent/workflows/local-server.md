---
description: Start or stop the local Jekyll development server using Docker
---

# Local Jekyll Development Server

This workflow manages the local Jekyll development server for previewing the al-folio site.

## Starting the Server

// turbo
1. Start the local development server:
```bash
cd /home/sisyphus/iiith/my-life && docker compose up -d
```

2. Wait for Jekyll to build (check logs):
```bash
cd /home/sisyphus/iiith/my-life && docker compose logs --tail=20
```

3. Open the site in browser at `http://localhost:8080`

## Stopping the Server

// turbo
1. Stop the local development server:
```bash
cd /home/sisyphus/iiith/my-life && docker compose down
```

## Viewing Logs

// turbo
1. View container logs:
```bash
cd /home/sisyphus/iiith/my-life && docker compose logs -f --tail=50
```

## Rebuilding After Config Changes

After modifying `_config.yml`, you need to restart the server:

// turbo
1. Restart the Jekyll container:
```bash
cd /home/sisyphus/iiith/my-life && docker compose restart
```

## Notes

- The site auto-reloads when you edit content files (posts, pages, etc.)
- Changes to `_config.yml` require a container restart
- LiveReload runs on port 35729
- The site is served on port 8080
