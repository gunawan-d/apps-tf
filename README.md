# Hello World Fullstack Application

Simple Hello World application with Go backend and vanilla JavaScript frontend.

## Project Structure

```
.
├── go.mod           # Go module dependencies
├── main.go          # Go backend server (Gin)
├── index.html       # Frontend HTML/JS
└── README.md        # This file
```

## Features

- **Backend (Go + Gin)**
  - `GET /` - Returns Hello World message with author
  - `GET /health` - Health check endpoint with timestamp

- **Frontend (Vanilla JS)**
  - Displays Hello World message from backend
  - Health status indicator (auto-refresh every 5s)
  - Manual health check button
  - Responsive design with gradient background

## Running the Application

### 1. Using Docker

**Build the Docker image:**
```bash
docker build -t hello-world-app .
```

**Run the container:**
```bash
docker run -d -p 8080:8080 --name hello-world hello-world-app
```

**Check logs:**
```bash
docker logs -f hello-world
```

**Stop the container:**
```bash
docker stop hello-world
docker rm hello-world
```

The backend will be available at `http://localhost:8080`.

**Using Docker Compose (optional):**
Create `docker-compose.yml`:
```yaml
version: '3.8'
services:
  backend:
    build: .
    ports:
      - "8080:8080"
    restart: unless-stopped
```
Run: `docker-compose up -d`

## API Endpoints

| Method | Endpoint | Description | Example Response |
|--------|----------|-------------|------------------|
| GET | `/` | Hello World message | `{"message":"Hello World from Go backend!","author":"gunawan"}` |
| GET | `/health` | Health check | `{"status":"healthy","timestamp":1714321234}` |
