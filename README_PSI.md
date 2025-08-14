# PSI Inventory

**PSI Inventory** is a customized inventory management system based on InvenTree, tailored for PSI's specific needs.

## Overview

This project uses InvenTree, an open-source inventory management system, configured for PSI's inventory tracking and management requirements.

## Quick Start

### Prerequisites
- Docker and Docker Compose
- Git

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/AdamManning/PSI-Inventory.git
   cd PSI-Inventory
   ```

2. **Start the system:**
   ```bash
   cd contrib/container
   docker-compose up -d
   ```

3. **Access the web interface:**
   - Open your browser and go to `http://localhost`
   - The system will automatically set up the database on first run (takes 2-3 minutes)

## Configuration

The system configuration is stored in `contrib/container/.env`:

- **Database:** PostgreSQL (configured automatically)
- **Cache:** Redis
- **Web Server:** Caddy (reverse proxy)
- **Application:** InvenTree stable version

## Data Persistence

All data is stored in Docker named volumes:
- `inventree-data`: Main application data
- `inventree-static`: Static web files
- `inventree-media`: Uploaded media files

## Development

This setup uses the stable InvenTree Docker images. For development or customization:

1. Check the official InvenTree documentation: https://docs.inventree.org/
2. Modify configuration in `contrib/container/.env`
3. Restart containers: `docker-compose restart`

## Monitoring

Check system status:
```bash
# View running containers
docker-compose ps

# Check logs
docker logs inventree-server
docker logs inventree-db

# Stop system
docker-compose down

# Start system
docker-compose up -d
```

## Support

For InvenTree-specific issues, refer to:
- [InvenTree Documentation](https://docs.inventree.org/)
- [InvenTree GitHub](https://github.com/inventree/InvenTree)

## Based on InvenTree

This project is built on [InvenTree](https://github.com/inventree/InvenTree), an open-source inventory management system.

InvenTree License: MIT License