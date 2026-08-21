We use [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/) to set up ROS2 and related nodes. This keeps host computers clean and allows easy (re)installation and redistribution of software. To keep things modular, we create a docker container for each set of related ROS2 nodes. This allows mix and match of (sets of) ROS2 nodes without having to rely on a single container that contains all possible nodes.

There are base images with a ROS2 installation, on top of which another container image with ROS2 nodes can be built. Yet another container image can be build on top of the resulting image, etc.

An example stack may be:
	- ros2_docker_reframectrl, built on top of
	- ros2_docker_bota, built on top of
	- ros2_docker_fr3, built on top of
	- ros2_docker_base

# Repositories

See [ros2 docker repositories](https://github.com/orgs/nakama-lab/repositories). 
Note that repositories may be hidden if you do not have the correct GitHub access rights.

# Building container images

- Before you build container images, consider that they might already have been build. See:

`$ docker image ls`

- To build an image, open a terminal
- Navigate to a repository, e.g.

`$ cd Documents/git/ros2_docker_base`

- Inspect the .env file and modify if necessary
	- On ubuntu, if the .env is hidden in the file explorer, press ctrl + H
	- For non-base images, you can use the .env file to indicate the image to build on top of. The image to build upon needs to be build first.
- Use docker compose to build the image:

`$ docker compose build`

- Consider adding the `--no-cache` flag to start the build process from scratch, without previously cached information:

`$ docker compose build --no-cache`

# Running container

- Open a terminal
- Navigate to a repository, e.g.

`$ cd Documents/git/ros2_docker_reframectrl`

- Start a container in detached mode

`$ docker compose up -d`

- Stop and clean up a container using:

`$ docker compose down`

# Inspecting container

- To move a terminal inside a running container, use:

`$ docker exec -it {container_name} bash`

- You can use the Tab button to auto-complete container names.
- You can detach the terminal from the container by typing `exit` or pressing `Ctrl + D`
