Autonomous Navigation Mobile Robot Simulation

Project Objectives

The goal of this project is to develop an autonomous mobile robot with real-time mapping and navigation capabilities using the Robot Operating System (ROS) and the Gazebo simulation platform. The project aims to create a robot that can autonomously explore and navigate an environment without relying on pre-saved maps.

Methods and Tools Used

ROS and Gazebo Simulation

ROS serves as a standard framework for developing robotic systems, while Gazebo simulates the physical environment for the robot. The TurtleBot3 robot model was used to simulate a real-world robotic system.

SLAM (Simultaneous Localization and Mapping)

The gmapping SLAM algorithm was employed to enable the robot to autonomously explore and map an unknown environment. This algorithm uses laser sensor data to create a map of the surroundings while determining the robot's position.

Frontier Exploration

Frontier exploration was utilized for autonomous exploration. This method enables the robot to target unknown regions of the map for discovery.

Navigation

The Move Base package was used to allow the robot to navigate to specified goals while avoiding obstacles. Global and local costmaps ensured that the robot followed an environment-aware path.

Challenges Encountered and Solutions

TF (Transform) Errors

Issue:

During navigation, the robot faced issues with TF transformations, particularly in the map -> odom and odom -> base_link chains.

Solution:

Proper initialization of robot_state_publisher and amcl nodes.

Verified transformation chains using the TF view frames command.

RViz Conflict

Issue:

Multiple RViz nodes were launched simultaneously, causing naming conflicts.

Solution:

Renamed the RViz node or manually launched it.

Costmap Issues

Issue:

Global and local costmaps failed to publish, hindering the robot's ability to plan a path.

Solution:

Reconfigured global_costmap_params.yaml and local_costmap_params.yaml files.

Verified data publication using:

rostopic echo /move_base/global_costmap/costmap
rostopic echo /move_base/local_costmap/costmap

Results

The project successfully achieved its objective of creating a robot simulation that operates without pre-saved maps. Using the gmapping algorithm, the robot explored its environment, expanded the map with frontier exploration, and avoided obstacles during navigation.

Video Presentation

Details of the project and simulation results are presented in the following video:

YouTube Video Link

https://youtu.be/A8_JgRBhRO4?si=tpJp8dbxpjxW3jx1

GitHub Repository

The project code, report, and video link can be accessed via the following GitHub repository:
