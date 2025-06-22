# Common Docker Commands for working with Images and Containers

This guide provides an overview of essential Docker commands to help you manage images and containers efficiently.

---

## 📦 Image Commands

### `docker image build`

Builds the docker image from the DockerFile.

```bash
docker image build
```

Alias: `docker build`

### `docker image ls`

List all Docker images present on your system.

```bash
docker image ls
```

Alias: `docker images`

Use this to see the repository, tag, image ID, creation date, and size of images.

---

### `docker image pull`

Download an image from a Docker registry (e.g., Docker Hub).

```bash
docker image pull <image_name>:<tag>
```

**Example:**

```bash
docker image pull ubuntu:20.04
```

Alias: `docker pull`

---

### `docker image rm`

Remove one or more Docker images from your system.

```bash
docker image rm <image_name_or_id>
```

**Example:**

```bash
docker image rm ubuntu:20.04
```

Alias: `docker rmi`

---

## 🏗 Container Commands

### `docker container run`

Create and start a new container from an image.

```bash
docker container run <options> <image_name>
```

**Example:**

```bash
docker container run -it ubuntu:20.04 bash
```

Alias: `docker run`

This is one of the most used commands to start working inside a container.

---

### `docker container ls`

List running containers.

```bash
docker container ls
```

Alias: `docker ps`

Add `-a` to see all containers (including stopped ones):

```bash
docker container ls -a
```


---

### `docker container rm`

Remove one or more containers.

```bash
docker container rm <container_id_or_name>
```

Alias: `docker rm`

---

### `docker container prune`

Remove all stopped containers to clean up system resources.

```bash
docker container prune
```

**Use with caution!** It will delete all stopped containers.

---

### `docker container start`

Start an existing (stopped) container.

```bash
docker container start <container_id_or_name>
```

Alias: `docker start`

---

### `docker container stop`

Stop a running container.

```bash
docker container stop <container_id_or_name>
```

Alias: `docker stop`

---

### `docker container exec`

Run a command in a running container.

```bash
docker container exec <options> <container_id_or_name> <command>
```

**Example:**

```bash
docker container exec -it my_container bash
```

Alias: `docker exec`

Use this to interactively work inside a running container.

---

## ✅ Summary

| Command | Purpose | Alias |
| :-- | :-- | :-- |
| `docker image ls` | List images | `docker images` |
| `docker image pull` | Download image | `docker pull` |
| `docker image rm` | Remove image | `docker rmi` |
| `docker container run` | Create and start container | `docker run` |
| `docker container ls` | List running containers | `docker ps` |
| `docker container rm` | Remove container | `docker rm` |
| `docker container prune` | Remove all stopped containers | - |
| `docker container start` | Start container | `docker start` |
| `docker container stop` | Stop container | `docker stop` |
| `docker container exec` | Run command in container | `docker exec` |


---

## 🔗 References

- [Docker CLI reference](https://docs.docker.com/reference/cli/docker/)
- [Docker images management](https://docs.docker.com/reference/cli/docker/image/)
- [Docker container management](https://docs.docker.com/engine/reference/commandline/container/)
