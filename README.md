# cartographer_ros_container

Cartographer ROS contained in Docker to prevent clashing between protobufs versions (Gazebo uses old version)

## Installation

1. [Install Docker](https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-using-the-repository)
2. Download this Docker Image tar file
3. Load the image to your Docker:

docker load -i <path to image tar file>

## Running Cartographer

1. Launch your robot (if in Gazebo, use some test room) with LIDAR sensor enabled
2. In a different shell, execute docker: 

docker run -it --rm --net=host compiled_cartographer_ros

3. Inside docker run:

roslaunch cartographer_ros backpack_2d.launch 

This line will expose your ROS network to Docker so Cartographer run like it would have if it was local
