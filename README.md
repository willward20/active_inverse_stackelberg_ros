# active_inverse_stackelberg_ros

ROS package for demonstrating active inverse stackelberg game research in Gazebo. Forked from Yue Yu and Jake Levy's [yueyu19/active_inverse_Stackelberg](https://github.com/yueyu19/active_inverse_Stackelberg) package. 

## Setup
- Install [conda miniforge](https://github.com/conda-forge/miniforge?tab=readme-ov-file#install):

      curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
      bash Miniforge3-$(uname)-$(uname -m).sh

- Install the RoboStack virtual environment ([source](https://answers.ros.org/question/386611/robostack-turtlebot3-teleop/)):

      conda create -n robostackenv python=3.8
      conda config --env --add channels conda-forge
      conda config --env --add channels robostack
      conda config --env --set channel_priority strict

- Activate the environment and install ROS/turtlebot3 packages ([source](https://answers.ros.org/question/386611/robostack-turtlebot3-teleop/)):

      conda activate robostackenv
      conda install -c robostack ros-noetic-turtlebot3
      conda install -c robostack ros-noetic-turtlebot3-gazebo
      conda install -c robostack ros-noetic-desktop-full

- Install ROS development tools using conda ([source](https://robostack.github.io/GettingStarted.html)):

      conda install compilers cmake pkg-config make ninja colcon-common-extensions catkin_tools rosdep

- Create a workspace with a src folder, if you do not already have one.
- Clone the [ros_sockets](https://github.com/CLeARoboticsLab/ros_sockets) package into the src folder of your workspace.
- Clone this package into the src folder of your workspace.
- Build the packages and source your workspace by cd'ing into your workspace directory and running:
 
      catkin_make
      . devel/setup.bash

  # Usage
  After following the steps above, run the leader/follower pursuit game with

      roslaunch active_inverse_stackelberg_ros pursuit.launch

  or run the driving assistant game with

      roslaunch active_inverse_stackelberg_ros driver.launch
 
  Then, start the Julia optimzation procedure (see other repository). 