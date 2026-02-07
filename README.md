# Docker Compose for Booking microservices

This folder contains Dockerfiles and a docker-compose.yaml to build and run the microservices stack locally.

Files:
- .env - environment variables used by docker-compose
- docker-compose.yaml - compose file to build and run services
- Dockerfile.* - per-service Dockerfiles for building images

Quick start (PowerShell):
1. From project root run (uses docker/.env):
   cd docker; docker-compose build
   docker-compose up -d

2. To view logs:
   docker-compose logs -f

3. To stop and remove containers:
   docker-compose down -v

Notes:
- By default this compose uses a single Postgres container. Adjust DB env variables in .env as needed.
- The user-service expects a keystore (`keystore.p12`) on its classpath. Place it under `docker/` and map into the image or mount as a volume if needed.
- If you want to mount local source and build inside containers, change build contexts or use mvn package locally and `image` tags.
