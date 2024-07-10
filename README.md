# Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt

## Description
This repository contains the necessary files and instructions to set up and control a robot arm using ROS Noetic and an Arduino. The project demonstrates two primary methods of controlling the robot arm:

1* Joint State Publisher: Basic control by publishing joint states.
2* MoveIt and Kinematics: Advanced control using MoveIt for motion planning and kinematics.

# Task3: Controlling the robot arm by joint_state_publisher 

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
   * Navigate to the src directory and clone the package repository:
     ```bash
     cd ~/catkin_ws/src
     sudo apt install git
     git clone https://github.com/smart-methods/arduino_robot_arm
     ```
   * Install all dependencies:
     ```bash
     cd ~/catkin_ws
     rosdep install --from-paths src --ignore-src -r -y
     sudo apt-get install ros-noetic-moveit ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
     sudo apt-get install ros-noetic-gazebo-ros-control ros-noetic-ros-controllers ros-noetic-ros-control
     ```
   * Compile the package:
     ```bash
     catkin_make
     ```

3. **Running the Package:**
   * Launch the package:
     ```bash
     roslaunch robot_arm_pkg check_motors.launch
     ```
   * Echo the joint states:
     ```bash
     rostopic echo /joint_states
     ```
   * If permissions are needed:
     ```bash
     cd ~/catkin_ws/src/arduino_robot_arm/robot_arm_pkg/scripts
     sudo chmod +x joint_states_to_gazebo.py
     ```
   * Launch the Gazebo simulation:
     ```bash
     roslaunch robot_arm_pkg check_motors_gazebo.launch
     rosrun robot_arm_pkg joint_states_to_gazebo.py
     ```

<p align="center">
  <img src="https://github.com/GDHadeel/Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt/assets/126657301/e7143047-eba2-4b71-835a-000f234ce17b" alt="Robotic Arm Image 1" width="400" height="400">
</p>

<p align="center">
  <img src="https://github.com/GDHadeel/Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt/assets/126657301/cfcb644f-8f63-4819-b1ab-1df37e8ae772" alt="Robotic Arm Image 1" width="400" height="400">
</p>

<p align="center">
  <img src="https://github.com/GDHadeel/Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt/assets/126657301/5a3538f2-9af0-4e79-b292-6805bf98e92f" alt="Robotic Arm Image 1" width="400" height="400">
</p>

---

# Task4: Controlling the robot arm by Moveit and kinematics

1. **Prerequisites:**
   * Ensure MoveIt is installed:
     ```bash
     sudo apt-get install ros-noetic-moveit
     ```
  
2. **Install the MoveIt Package:**
   * Clone the MoveIt package repository:
     ```bash
     cd ~/catkin_ws/src
     git clone https://github.com/smart-methods/arduino_robot_arm
     cd ~/catkin_ws
     rosdep install --from-paths src --ignore-src -r -y
     ```
   * Compile the workspace:
     ```bash
     catkin_make
     ```

3. **Running the MoveIt Package:**
   * Launch the MoveIt demo:
     ```bash
     roslaunch moveit_pkg demo.launch
     ```
   * Launch the Gazebo simulation with MoveIt:
     ```bash
     roslaunch moveit_pkg demo_gazebo.launch
     ```
     

<p align="center">
  <img src="https://github.com/GDHadeel/Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt/assets/126657301/9861e4b1-27a5-4167-94c0-c9b2c29dd7c0" alt="Robotic Arm Image 1" width="400" height="400">
</p>

<p align="center">
  <img src="https://github.com/GDHadeel/Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt/assets/126657301/50634cc3-bca0-4524-aa21-4ae29450caaa" alt="Robotic Arm Image 1" width="400" height="400">
</p>

## Acknowledgements

http://wiki.ros.org/catkin/Tutorials/create_a_workspace

https://www.youtube.com/watch?v=AFdGoBEVm2Y&list=PLvG04RqmBajDdTTFSdMC9Wi4duqejaKu1&index=2

https://drive.google.com/file/d/13Zwar6_7NBtJJoh1Uhmcws74_DmFbx__/view




