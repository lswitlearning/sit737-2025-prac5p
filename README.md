## Hello Docker Health Check App
This is a simple web application built with Node.js and Express, designed to demonstrate basic containerisation using Docker.  
The app is packaged into a Docker container and managed with Docker Compose, including health checks and automatic restarts.

### Required tools
- Git
- Visual Studio code
- Node.js
- Docker

### Installation
1. Clone the repository:
```
git clone https://github.com/lswitlearning/sit737-2025-prac5p.git
```

2. Install required dependencies:
```
npm install
```

### Usage Without Docker
1. Start the server:
```
node app.js
```
2. Access the app:
Home: http://localhost:3000
Health: http://localhost:3000/health

### Usage With Docker Compose
1. Build and start the app with Docker:
```
docker compose up --build
```
2. Access from your browser:
App: http://localhost:8081
Health: http://localhost:8081/health

3. Check container health:
```
docker ps
```
Look for status like:
```
STATUS: Up 20 seconds (healthy)
```

### Health Check & Restart
- Docker Compose is configured to monitor `/health` every 10 seconds.
- If the app becomes unresponsive (non-200 or timeout), it's marked as `unhealthy`.
- With `restart: always`, Docker automatically restarts the container.