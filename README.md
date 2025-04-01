# UX Stack

This repository contains the deployment configuration for running the UI and Backend services of the project.

## Prerequisites

- Docker Engine
- Docker Compose
- VPN connection to "calypso" (see [wiki.isc-vs.ch](https://wiki.isc-vs.ch/doku.php?id=infra:wireguard))

## Quick Start

1. Clone this repository:
```bash
git clone https://github.com/6figuress/ux-stack
cd ux-stack
```

2. Start the application:
```bash
docker compose up -d
```

The application will be available at:
- Frontend: http://localhost:8888
- Backend API: http://localhost:5000

## Architecture

The stack consists of two main services : the frontend UI and the backend, a wrapper for the calypso-hosted texturing and rendering APIs.

They are each documented in their respective repositories ; [Frontend](https://github.com/6figuress/ui) and [backend](https://github.com/6figuress/TCP).

## Configuration

The services are configured to communicate over a dedicated bridge network and automatically restart unless stopped manually.

## Common Commands

### Start the stack
```bash
docker compose up -d
```

### Stop the stack
```bash
docker compose down
```

### Update images to latest version
```bash
docker compose pull
docker compose up -d
```

### Check service status
```bash
docker compose ps
```
