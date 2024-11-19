# CodeSmithy - Bootstrap Build Prerequisites Docker Images

Configuration files for [Docker](https://www.docker.com/) images that contain the necessary prerequisites to
build the CodeSmithy code.

The images are available from [Docker Hub](https://hub.docker.com/r/codesmithy/gcc-bootstrap-build-prerequisites).

# Image Contents

# Upload Instructions

```
docker build . --no-cache
docker tag <id> codesmithy/gcc-bootstrap-build-prerequisites:latest
docker tag <id> codesmithy/gcc-bootstrap-build-prerequisites:<version>
docker login
docker push codesmithy/gcc-bootstrap-build-prerequisites:latest
docker push codesmithy/gcc-bootstrap-build-prerequisites:<version>
```
