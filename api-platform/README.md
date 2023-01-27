## https://api-platform.com/docs/distribution/
## In 
git checkout v3.0.9
docker compose build --pull --no-cache

docker image tag api-platform-docker-php:latest registry.h8l.io/karbon/api-platform-php:3.0.9
docker image tag api-platform-docker-caddy:latest registry.h8l.io/karbon/api-platform-daddy:3.0.9
docker image tag api-platform-docker-pwa:latest registry.h8l.io/karbon/api-platform-pwa:3.0.9

docker push registry.h8l.io/karbon/api-platform-php:3.0.9
docker push registry.h8l.io/karbon/api-platform-daddy:3.0.9
docker push registry.h8l.io/karbon/api-platform-pwa:3.0.9