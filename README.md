# Different ways of building images for Spring Boot applications

In this repository you will find the source code for the blog posts:

* [How to use Spring Boot with Google Distroless Container Images?](https://solureal.com/blogs/how-to-use-google-distroless-docker-images-with-spring-boot)

## Dockerfiles:

* Dockerfile: [Google Distroless](https://github.com/GoogleContainerTools/distroless) based image

```bash
docker build -t spring-demo-distroless .
```

* Dockerfile-debug: [Google Distroless](https://github.com/GoogleContainerTools/distroless) based image with a shell for
  debugging

```bash
docker build -t spring-demo-distroless-debug -f Dockerfile-debug .
```

* Dockerfile-jdk: bellsoft/liberica-openjre-alpine:17 based image that contains only a JRE for a smaller image.
```bash
docker build -t spring-demo-jre -f Dockerfile-jdk .
```
To build the image with buildpacks:

```bash
./gradlew bootBuildImage
```

## Image size

See the image size of the images build:
```bash
docker images | grep spring-demo
```