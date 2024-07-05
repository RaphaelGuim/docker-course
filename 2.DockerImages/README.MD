# DOCKER

- CONTAINER - The running "unit of software"
- IMAGES - Template / Blueprints for containers. Contais code + required tools

You can create multiple Containers based on a Image.


We need an Image to build a Container.

This command bellow will download from DockerHub the image and build it in your machine.

```
docker run node
```

 

Use this **-a** flag to expose a interative terminal inside this image.
- **docker run -it node**: 

## Useful Docker Command
```
docker ps
```
Use **-a** flag to including those that are stopped.
- **docker -a ps**

--- 
To run a image you should add the flag **-p localport:exposedPort**
```
docker run -p 3000:80 DOCKERIMAGE
```