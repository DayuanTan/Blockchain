
# Docker

- Official tutorial:
    - https://docs.docker.com/get-started/
    - relative code:
        /Users/dyt/docker/docker101tutorial/app/app/Dockerfile
- container: 
  - is a sandboxed process on your machine that is isolated from all other processes on the host machine.
  - is a runnable instance of an image. You can create, start, stop, move, or delete a container using the DockerAPI or CLI.
  - can be run on local machines, virtual machines or deployed to the cloud.
  - is portable (can be run on any OS).
  - is isolated from other containers and runs its own software, binaries, and configurations.
- image:
  - When running a container, it uses an isolated filesystem. This custom filesystem is provided by a container image. 
  - Since the image contains the container’s filesystem, it must contain everything needed to run an application - all dependencies, configurations, scripts, binaries, etc. The image also contains other configuration for the container, such as environment variables, a default command to run, and other metadata.
- Dockerfile: 
  - is simply a text-based script of instructions that is used to create a container image. 
- build an  image
  - build the container image using the docker build command.

    ```$ docker build -t getting-started .``` (must have Dockerfile created.) This command used the Dockerfile to build a new container image.

- Run an App Container
  
    Now that we have an image, let's run the application! To do so, we will use the docker run command.

    Start your container using the docker run command and specify the name of the image we just created:

    ```docker run -dp 3000:3000 getting-started```

- Stop and remove a container
    - ```docker ps```
    - ```docker stop <the-container-id>```
    - ```docker rm <the-container-id>```
    - every time we make a change in  our code we need to rebuild and start a new container (later will do persistence to avoid this)

- Container Volumes (to persist the data)
   - each container starts from the image definition each time it starts. While containers can create, update, and delete files, those changes are lost when the container is removed and all changes are isolated to that container. With volumes, we can change all of this.
  - Volumes provide the ability to connect specific filesystem paths of the container back to the host machine. If a directory in the container is mounted, changes in that directory are also seen on the host machine. If we mount that same directory across container restarts, we'd see the same files.
  - two main types of volumes: ()
    - named volume, 
    - bind mounts
- More about named volume, bind mounts, share to hub, multiple containers, docker compose go to https://docs.docker.com/get-started/ or http://localhost/tutorial/ after run locally