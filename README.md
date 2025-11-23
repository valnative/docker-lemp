# LEMP Docker

## Description
Lightweight LEMP (Linux, Nginx, MySQL/MariaDB, PHP-FPM) stack configured for local development using Docker Compose. Provides a reproducible environment for PHP applications with an isolated webserver, PHP runtime, and database.

## Requirements
- Docker Engine (recommended: latest stable)
- Docker Compose (or Docker CLI plugin `docker compose`)
- Git (to clone the repository)
- Minimum 2GB free RAM for containers
- Optional: .env file editor (text editor / VS Code)

## Installation
1. Clone the repository:
    ```
    git clone git@github.com:valnative/docker-lemp.git
    cd docker-lemp
    ```
2. Copy and configure environment:
    ```
    cp .env.example .env
    # Edit .env to set DB credentials, ports, etc.
    ```
3. Start services:
    ```
    docker compose up -d --build
    ```
4. Verify:
    - Web: http://localhost (or custom PORT in .env)
    - DB: connect to host `127.0.0.1` and configured port
5. Stop services:
    ```
    docker compose down
    ```

Notes:
- Keep secrets out of the repository; use .env and Docker secrets for sensitive data.
- Customize ports and volumes via .env or docker-compose.yml as needed.
- Add healthchecks and backups for production-like resilience.