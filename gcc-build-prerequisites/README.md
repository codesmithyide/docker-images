# CodeSmithy - Build Prerequisites Docker Images

Configuration files for [Docker](https://www.docker.com/) images that contain the necessary prerequisites to
build the CodeSmithy code.

The images are available from [Docker Hub](https://hub.docker.com/r/codesmithy/gcc-build-prerequisites).

# Image Contents

# Upload Instructions

```
docker build . --no-cache
docker tag <id> codesmithy/gcc-build-prerequisites:latest
docker tag <id> codesmithy/gcc-build-prerequisites:<version>
docker login
docker push codesmithy/gcc-build-prerequisites:latest
docker push codesmithy/gcc-build-prerequisites:<version>
```
