# Indoor Localization and Mapping System for Obstacle Detection using LiDAR and SLAM
# Purpose

The purpose of this project is to design and develop an intelligent indoor localization system capable of:

Scanning indoor environments in real time

Creating accurate maps (Top view and Front view)

Detecting obstacles present in pathways

Providing spatial awareness for navigation

Helping robots or assistive systems navigate safely indoors

# This system is especially useful in environments where GPS does not work, such as:

Hospitals

Shopping malls

Airports

Warehouses

Smart homes

Assistive systems for disabled individuals (related to your AccessRoute project domain)

# Introduction (What it Works)
# Overview

Indoor localization refers to determining the position of an object or robot inside a building without using GPS.

This project uses:

Sensors (LiDAR / Depth camera / Ultrasonic)

SLAM algorithm (Simultaneous Localization and Mapping)

Processing unit (Raspberry Pi / Jetson Nano / Laptop)

# Visualization software

The system performs three main tasks:

Step 1: Scanning

Sensors scan surroundings and collect distance data from obstacles.

Step 2: Localization

The system calculates its current position inside the environment.

Step 3: Mapping

The system generates:

Top view map (2D map)

Front view map (Obstacle view ahead)

# Working Principle

Input → Sensor Data
Processing → SLAM Algorithm
Output → Map + Obstacle Detection + Localization

Output Generated

1. 2D Top view map

2. Front view obstacle map

3. Real-time position tracking

4. Obstacle distance detection


# Approaches, Algorithms, and Applications
# Approach 1: LiDAR-Based SLAM
Algorithm Used

SLAM (Simultaneous Localization and Mapping)

Popular SLAM Algorithms:

GMapping

Hector SLAM

Cartographer (Google)

ORB-SLAM

RTAB-Map

Working

LiDAR sends laser beams → measures distance → builds environment map

Advantages

High accuracy

Reliable

Works in low light

Applications

Autonomous robots

Warehouse robots

Indoor navigation

# Approach 2: Camera-Based Localization (Visual SLAM)
# Algorithm Used

ORB-SLAM

Visual Odometry

Feature detection (ORB, SIFT, SURF)

Working

Camera captures images → detects features → builds map

Advantages

Low cost

Works without LiDAR

Applications

Mobile robots

AR/VR systems

Indoor navigation

# Approach 3: Sensor Fusion Approach

# Combines multiple sensors:

LiDAR

IMU

Camera

Uses:

Extended Kalman Filter (EKF)

Advantages:

Higher accuracy

More reliable

Applications:

Autonomous vehicles

Advanced robots

# Approach 4: Grid Mapping Algorithm

# Creates occupancy grid map

Map consists of:

Free space

Obstacle space

Unknown space

Applications:

Robot navigation

Path planning


# Hardware Constraints (Specifications)
Option 1: Recommended Hardware (Best)
Processing Unit

Jetson Nano / Raspberry Pi 4 / Laptop

Specifications:

CPU: Quad Core

RAM: 4GB minimum (8GB recommended)

Storage: 32GB minimum

Sensor 1: LiDAR Sensor

Example:

RPLIDAR A1/A2

Specifications:

Range: 0.15m to 12m
Accuracy: ±2cm
Scan rate: 5–10 Hz
Field of view: 360°

Sensor 2: Depth Camera (Optional)

Example:

Intel RealSense D435

Range: 0.2m to 10m

Sensor 3: IMU Sensor

Example:

MPU6050

Purpose:

Orientation detection

Power Supply

Battery: 5V / 12V power supply

Additional Hardware

Robot chassis (optional)
Motor driver (optional)
Wheels (optional)

5. Software Requirements

Operating System:

Ubuntu 20.04 or 22.04

Software:

ROS (Robot Operating System)

Libraries:

OpenCV

SLAM libraries

Python / C++

Visualization tool:

RViz

6. System Architecture

Flow:

Sensor → ROS → SLAM Algorithm → Map Generation → Visualization

Output:

Top View Map
Front View Map
Obstacle Detection

7. Expected Output

The system will generate:

Top View:

2D grid map

Shows obstacles and free paths

Front View:

Distance of obstacle ahead

Useful for navigation

Localization:

Shows robot position on map

8. Applications

This system can be used in:

Healthcare

Wheelchair navigation

Assistive robots

Warehouses

Autonomous robots

Smart buildings

Security robots

Military

Indoor reconnaissance

Shopping malls

Navigation assistance

# PART 1: System Overview

Goal:

• Scan indoor environment
• Detect obstacles
• Generate map (Top view)
• Detect front obstacles
• Visualize in RViz
• Simulate in Gazebo

System:

Sensor → ROS → SLAM → Map → Visualization


# PART 2: Install Required Software
Step 1: Install Ubuntu

Recommended:
Ubuntu 20.04

# Step 2: Install ROS Noetic

Open terminal:

sudo apt update
sudo apt install ros-noetic-desktop-full

Initialize ROS:

sudo rosdep init
rosdep update

Add ROS to bash:

echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

# Step 3: Install Required Packages
sudo apt install ros-noetic-slam-gmapping
sudo apt install ros-noetic-navigation
sudo apt install ros-noetic-turtlebot3*
sudo apt install ros-noetic-gazebo-ros
sudo apt install ros-noetic-rviz
sudo apt install python3-pip
pip3 install numpy matplotlib
PART 3: Create ROS Workspace
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin_make

# Activate workspace:

echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
# PART 4: Python Code – Obstacle Detection (Front View)
Create package
# Project Folder Structure
catkin_ws/
 ├── src/
 │   ├── indoor_mapping/
 │   │   ├── scripts/
 │   │   │   ├── obstacle_detector.py
 │   │   ├── package.xml
 │   │   ├── CMakeLists.txt

# Conclusion

Conclusion Example:

The Indoor Localization and Mapping System successfully detects obstacles and generates real-time top and front view maps using SLAM algorithms. This system can be used for autonomous navigation, assistive robotics, and smart indoor environments.