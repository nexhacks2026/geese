# Goosepedia

The definitive archive dedicated to the world's most misunderstood waterfowl: The Goose.

## Overview

Goosepedia is a simple, informational website exploring the anatomy, diet, and social structures of geese.

## Features

- **Semantic HTML5**: Clean structure.
- **Responsive Design**: Works on mobile and desktop.
- **Anatomy & Diet**: Detailed pages about goose biology.

## Structure

- `index.html`: The main landing page.
- `anatomy.html`: Detailed breakdown of goose physiology.
- `diet.html`: Information on feeding habits.
- `style.css`: The core stylesheet.

## Developer Environment

To facilitate future complex deployments and ensure a consistent development experience, we recommend using a containerized workflow.

### Local Development

You can serve the static site locally using any standard HTTP server.

**Python:**
```bash
python3 -m http.server 8000
```
Then visit `http://localhost:8000`.

**Node.js:**
```bash
npx http-server .
```

### Docker Deployment

For production-ready deployments, we use Nginx in a Docker container.

**Dockerfile Template:**
```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
```

**Docker Compose Template (for local dev):**
```yaml
version: '3.8'
services:
  goosepedia:
    build: .
    ports:
      - "8080:80"
    volumes:
      - .:/usr/share/nginx/html
```

These configurations ensure that the application can be easily orchestrated in more complex environments (e.g., Kubernetes, ECS) in the future.
