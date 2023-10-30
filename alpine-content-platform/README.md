# Upload Instructions

```
docker build --no-cache .
docker tag <id> ghcr.io/codesmithyide/alpine-content-platform:latest
docker tag <id> ghcr.io/codesmithyide/alpine-content-platform:<version>
docker login ghcr.io
docker push ghcr.io/codesmithyide/alpine-content-platform:latest
docker push ghcr.io/codesmithyide/alpine-content-platform:<version>
```
