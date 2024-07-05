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

Docker Images is a static photo of your app. If you change the source code, there is no impact in your images.

# Images are Layer Based.

When building a Docker image from a Dockerfile (a file that defines the steps to create the image), each instruction in the Dockerfile creates a new layer.

## Benefits of Layers:

* Reusability:

    Layers can be reused between different images. If two images share the same layer (for example, the base layer ubuntu:latest), Docker stores this layer only once, saving space.
* Efficiency:

    When you modify an image and rebuild the container, **Docker reuses unchanged layers from the cache**, speeding up the build process.
* Versioning:

    Each layer represents a state of the filesystem. This allows you to revert to a previous state or track changes.

To visualize the layers, use the command:
```
docker history <image_name>
```

When one layer changes Docker rebuilds all subsequent layers

--- 

* **docker run**: Always creates a new container and runs it in the foreground.
* **docker run -p LOCALPORT:APPPORT id**: Starts the container in foreground. Use the ID of an existing Docker image to base it on.
* **docker start <name/id>**: Starts the container in the background. Add the **-a** flag to bring it to the foreground.
* **docker attach <name/id>**: Attaches to a running Docker container and brings it to the foreground in the terminal.

---

* **docker run -it <id>**: Uses flags **-i** for input and **-t** for an integrated terminal. This is used because **docker run** alone does not allow interaction.
* **docker start -ai <id>**: Uses flags **-a** for foreground and **-i** for input. This is used because **docker run** alone does not allow interaction.

---

* **docker container prune**: Deletes all stopped containers.
* **docker image prune -a --force**: Cleans up unused images from your local system.

    - **-a, --all**: Remove all unused images, not just dangling ones.
    
    - **--force**: Skip the confirmation prompt and force removal of images.

---

### Docker `rm` Command

- **Purpose**: Removes one or more Docker containers.
- **Usage**: 
  - `docker rm CONTAINER_ID`: Removes a specific container by its ID.
  - `docker rm $(docker ps -a -q)`: Removes all stopped containers.
- **Options**: 
  - `-f, --force`: Forcefully removes running containers.
  - `-v, --volumes`: Removes associated volumes.

### Docker `rmi` Command

- **Purpose**: Removes one or more Docker images.
- **Usage**: 
  - `docker rmi IMAGE_ID`: Removes a specific image by its ID or tag.
  - `docker rmi $(docker images -q)`: Removes all images.
- **Options**: 
  - `-f, --force`: Forcefully removes tagged images.
  - `-a, --all`: Removes all images, including dangling ones.

These commands are essential for managing Docker containers and images on your local system, providing efficient cleanup and resource management capabilities.

---
* **docker run --rm <ID>** removes a container when it is stoped.