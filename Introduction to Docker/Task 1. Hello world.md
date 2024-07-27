## Task 1. Hello world
1.In Cloud Shell enter the following command to run a hello world container to get started:
```bash
docker run hello-world
```
(Command Output)

```bash
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
9db2ca6ccae0: Pull complete
Digest: sha256:4b8ff392a12ed9ea17784bd3c9a8b1fa3299cac44aca35a85c90c5e3c7afacdc
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
...
```

This simple container returns Hello from Docker! to your screen. While the command is simple, notice in the output the number of steps it performed. The Docker daemon searched for the hello-world image, didn't find the image locally, pulled the image from a public registry called Docker Hub, created a container from that image, and ran the container for you.

2.Run the following command to take a look at the container image it pulled from Docker Hub:
```bash
docker images
```
(Command Output)

```bash
REPOSITORY     TAG      IMAGE ID       CREATED       SIZE
hello-world   latest    feb5d9fea6a5   14 months ago   13.3kB
```

This is the image pulled from the Docker Hub public registry. The Image ID is in SHA256 hash format—this field specifies the Docker image that's been provisioned. When the Docker daemon can't find an image locally, it will by default search the public registry for the image.

3.Run the container again:
```bash
docker run hello-world
```
(Command Output)

```bash
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
...
```
Notice the second time you run this, the Docker daemon finds the image in your local registry and runs the container from that image. It doesn't have to pull the image from Docker Hub.

4.Finally, look at the running containers by running the following command:
```bash
docker ps
```
(Command Output)
```bash
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS      PORTS               NAMES
```
There are no running containers. You already exited the hello-world containers you previously ran.

5.In order to see all containers, including ones that have finished executing, run
```bash
docker ps -a
```
(Command Output)
```bash
CONTAINER ID      IMAGE           COMMAND      ...     NAMES
6027ecba1c39      hello-world     "/hello"     ...     elated_knuth
358d709b8341      hello-world     "/hello"     ...     epic_lewin
```
This shows you the `Container ID`, a UUID generated by Docker to identify the container, and more metadata about the run. The container `Names` are also randomly generated but can be specified with` docker run --name [container-name] hello-world`.