# Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt

## Description
This repository contains the necessary files and instructions to set up and control a robot arm using ROS Noetic and an Arduino. The project demonstrates two primary methods of controlling the robot arm:

1- Joint State Publisher: Basic control by publishing joint states.
2- MoveIt and Kinematics: Advanced control using MoveIt for motion planning and kinematics.

# Task4: Controlling the robot arm by joint_state_publisher 

1. **Set Up ROS Environment:**
   * Ensure you have ROS Noetic installed.
   * Source the ROS environment:
     ```bash
     source /opt/ros/noetic/setup.bash
     ```
   * Create a ROS workspace:
     ```bash
     mkdir -p ~/catkin_ws/src
     cd ~/catkin_ws/
     catkin_make

     ```
   * Source the workspace:
     ```bash
     source devel/setup.bash
     echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
     ```
     
2. **Install the Package:**
   * Navigate to the 'src' directory and clone the package repository:

   * Source the ROS environment:
     ```bash
     source /opt/ros/noetic/setup.bash
     ```






     
---

# Task5: Controlling the robot arm by Moveit and kinematics
