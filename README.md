# Purbank - Getting Started

## Prerequisites

- Docker and Docker Compose installed
- Ports 80, 443

## Quick Start

### 1. Clone or Download the Project Files

Make sure you have the following files in your project directory:
- `docker-compose.yml`
- `Caddyfile`
- `.env.example`

### 2. Configure Environment Variables

Copy the example environment file:

```bash
cp .env.example .env
```

Edit the `.env` file and configure the required variables:

```bash
# Required - Generate a secure random string for JWT
JWT_SECRET_KEY=your-super-secret-key-here

# Required - Your email password for sending verification emails
MAIL_PASSWORD=your-email-password-here
```

### 3. Start the Application

Run the following command:

```bash
docker-compose up -d
```

This will:
- Download all required Docker images
- Start PostgreSQL database
- Start the backend API
- Start the frontend web app
- Configure Caddy as the reverse proxy

### 4. Access the Application

Once all services are running:

- **Frontend**: http://localhost
- **Backend API**: http://localhost/api/v1
- **Swagger Documentation**: http://localhost/swagger-ui/index.html

A default admin user will be created:
Email: admin@purbank.ch
Password: admin123

### 5. Check Service Status

View running containers:

```bash
docker-compose ps
```

View logs:

```bash
# All services
docker-compose logs -f

# Specific service
docker-compose logs -f backend
docker-compose logs -f frontend
docker-compose logs -f caddy
```

## Stopping the Application

```bash
docker-compose down
```

To also remove volumes (database data):

```bash
docker-compose down -v
```
