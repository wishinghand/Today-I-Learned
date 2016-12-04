>Copied from https://github.com/cameronwilby/til/blob/master/docker/docker-basics.md
# Docker

Docker is a "software containerization platform".

It provides a way to run applications securely isolated in a **container**, packaged with all it's dependencies and libraries - essentially making your applications portable.

## Verbage
- **Dockerfile**: A file that defines how to build the Image
- **Image**: A file that defines the environment for running the application. (Analogy: Like a class)
- **Container**: A secure isolation of your application, packaged with all it's dependencies and libraries. Or, a running instance of a Docker Image. (Analogy: Like an object)
- **Docker Hub**: A hosted registry service for managing and building images.
- **Docker Cloud**: A hosted service for building, testing and deploying docker images to your hosts.
- **Docker Trusted Registry**: Stores and signs your images
- **Docker Compose**: Define applications built using multiple containers.


## Benefits/Drawbacks

### Benefits
- Because your app always runs in the same environment, Docker simplifies testing and deployment.
- Because containers run without a hypervisor, you can run many applications on a single kernel, each one never interfering with eachother.
- You can get more out of your hardware by shifting the "unit of scale" from a virtual or physical machine to a container instance.


## Example Docker File
```docker
// Specifies the source image to use from the Docker Registry
FROM microsoft/dotnet:latest

// Copies your code to the docker VM, then restores nuget and builds.
COPY . /app
WORKDIR /app
RUN ["dotnet", "restore"]
RUN ["dotnet", "build"]

// Exposes port 5000
EXPOSE 5000/tcp

// Runs the application on port 5000
CMD ["dotnet", "run", "--server.urls", "http://*:5000"]
```

## Example Docker Commands

**Creates an image based on the Dockerfile in the current directory**<br />
`docker build -t <image_name> .`

- The -t argument assigns a tag to this image

**Start the container and launch your service**<br />
`docker run -d -p <host_port>:<container_port> --name <container_name> <image_name>`

- The `-d` option runs the container detached from the current terminal.
- The `-p` argument indicates the port mapping between the service and host.
    - `80:5000` maps local port 80 to container port 5000.
- The `--name` argument names your running container.

**See what docker images are running as containers**<br />
`docker ps`

**Attach to a running docker container so that you can see the log information**<br />
`docker attach --sig-proxy=false <container_name>`

- The `--sig-proxy=false` argument makes it so `Ctrl-C` cancels the `docker attach` process rather than the process running in the container process.

**Stop a running docker container**<br />
`docker stop <container_name>`

**Remove a docker container from your machine**<br />
`docker rm <container_name>

**Remove a docker image from your machine**<br />
`docker rmi <image_name>