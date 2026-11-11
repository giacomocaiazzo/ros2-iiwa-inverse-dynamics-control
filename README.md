# ROS 2 IIWA Position and Inverse Dynamics Control

**Contributors:** Marco Bartone, Giacomo Caiazzo, Matteo De Simone and Nicola Monetti.

### Overview
A ROS 2 workspace for simulating an iiwa manipulator with position control and inverse-dynamics torque control. The project explores joint-space and operational-space controllers using Gazebo and KDL.

### Usage

Open the terminal, open the container and enter into the directory where you want to download the folder, then download it with:

      $ git clone https://github.com/giacomocaiazzo/ros2-iiwa-inverse-dynamics-control.git
      $ cd ros2-iiwa-inverse-dynamics-control

-------------------------------


To build the packages, access the ROS2 workspace and build them with:

      $ colcon build

After this, use the source command:

      $ source install/setup.bash

Run the simulations of the manipulator robot using the position controller with:

      $ ros2 launch iiwa_bringup iiwa.launch.py
      
      
 In order to use the torque controller, launch the simulations with:
 
      $ ros2 launch iiwa_bringup iiwa.launch.py command_interface:="effort" robot_controller:="iiwa_arm_torque_controller"
 To perform a zero-gravity simulation, change the values of gravity in the empty.world file in the ros2_iiwa/iiwa_description/gazebo/worlds/(line 16):
      
      <gravity>0 0 0</gravity>
 
 Last thing, be sure to press the play button of the gazebo simulation in time, otherwise the controllers won't be loaded correctly.     

--------------------------------

Open another terminal, connect to the same docker container and use the following commands in the ROS2 workspace to run the node:

      $ source install/setup.bash
      $ ros2 run ros2_kdl_package ros2_kdl_node


