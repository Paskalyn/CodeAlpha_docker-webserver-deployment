# Docker Containerization Basics

## Project Overview
This project demonstrates Docker containerization by deploying and managing an NGINX web server inside a Docker container on an AWS EC2 instance.

The project covers:
- Docker installation and configuration
- Building Docker images
- Running and managing containers
- Container lifecycle management
- Monitoring container health
- Troubleshooting Docker issues
- Best practices for containerized deployment

---

## Technologies Used
- Docker
- NGINX
- AWS EC2
- Linux (Amazon Linux)
- Git & GitHub

---

## Project Structure

```bash
docker-web-project/
│
├── app/
│   └── index.html
│
├── screenshots/
│
├── Dockerfile
├── .dockerignore
└── README.md
```

---

## Dockerfile

```dockerfile
FROM nginx:latest

COPY app/index.html /usr/share/nginx/html/index.html

EXPOSE 80
```

---

## Build Docker Image

```bash
docker build -t nginx-webserver .
```

---

## Run Docker Container

```bash
docker run -d -p 8080:80 --name nginx-container nginx-webserver
```

---

## Verify Running Containers

```bash
docker ps
```

---

## Monitor Container

### View Logs

```bash
docker logs nginx-container
```

### Monitor Resource Usage

```bash
docker stats
```

---

## Container Lifecycle Commands

### Stop Container

```bash
docker stop nginx-container
```

### Start Container

```bash
docker start nginx-container
```

### Restart Container

```bash
docker restart nginx-container
```

### Remove Container

```bash
docker rm -f nginx-container
```

---

## Troubleshooting

### Port Conflict Error

Example:

```bash
Bind for 0.0.0.0:8080 failed: port is already allocated
```

### Solution

Use another port:

```bash
docker run -d -p 9090:80 nginx
```

---

## Best Practices
- Use lightweight Docker images
- Expose only required ports
- Monitor container resource usage
- Use .dockerignore
- Remove unused containers and images
- Use versioned image tags

---

## Learning Outcomes
Through this project, I learned:
- Docker containerization fundamentals
- Container lifecycle management
- Web server deployment inside containers
- Docker monitoring and troubleshooting
- Best practices for containerized applications

---

## Author
Paschaline Azokam
