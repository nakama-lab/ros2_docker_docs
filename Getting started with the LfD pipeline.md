# 1) Start ros2_docker container

- A docker container with all required nodes needs to be started.
	- See [[ros2_docker stack]] and the READMEs in the related repositories

# 2) Start robot and FCI

- The robot has to be started in FCI mode. See [[Robot start and stop]].
- When using additional equipment such as force sensors, cameras, and/or microphone, make sure they are plugged in and powered.

# 3) Start UI

- The UI should help you avoid writing ROS commands and launch scripts.
- Always stay clear of the robot and keep the emergency stops nearby when starting controllers!
- See [ros2_docker_ui](https://github.com/nakama-lab/ros2_docker_ui) and its README


