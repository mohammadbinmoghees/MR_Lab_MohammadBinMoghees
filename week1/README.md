# Week 1 ROS 2 Lab

## Brief Description of Week 1 Lab

The objective of this lab was to become familiar with the basic structure and workflow of ROS 2. In this lab, a ROS 2 workspace was created and a Python-based ROS 2 package named `my_first_pkg` was developed. The package was compiled using the `colcon build` tool and then executed using ROS 2 command-line tools. This lab introduced the fundamental ROS 2 concepts such as workspaces, packages, nodes, and the ROS 2 build system.

## Commands Used

The following commands were used during the lab:

```
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws

ros2 pkg create --build-type ament_python my_first_pkg

colcon build

source install/setup.bash

ros2 pkg list | grep my_first_pkg

ros2 run my_first_pkg <node_name>
```

Additional commands were also used to verify the ROS 2 installation and inspect the workspace environment.

## Problems Faced and Solutions

One issue encountered during the lab was that the ROS 2 package did not appear when running `ros2 pkg list`. This occurred because the workspace environment had not been sourced. The issue was resolved by running `source install/setup.bash`, which updated the environment variables and allowed ROS 2 to recognize the newly created package.

Another issue occurred when attempting to check the ROS version using `ros2 --version`, which produced an error because ROS 2 does not support that argument. Instead, commands such as `ros2 pkg list` and `ros2 doctor` were used to confirm that ROS 2 was installed and functioning correctly.

## Reflection

This lab provided a practical introduction to the ROS 2 development environment. Creating a workspace and building a package demonstrated how ROS 2 projects are structured and managed. The lab also emphasized the importance of properly configuring the environment, especially sourcing the workspace before running ROS commands. Learning how to build packages using `colcon` and execute nodes using `ros2 run` is essential for developing robotics applications in ROS 2. Overall, the lab helped build a foundation for understanding the modular architecture of ROS 2. It also improved familiarity with Linux terminal commands and ROS tools that will be used throughout future robotics labs.
