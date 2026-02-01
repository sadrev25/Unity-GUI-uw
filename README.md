# # Unity Underwater Robot GUI

This repository contains a Unity-based graphical interface developed
for academic purposes to visualize and monitor underwater robotic systems.
The project focuses on real-time data display from ROS2-based simulations
or underwater robot environments.

The GUI is designed to work with Unity simulations or external underwater
simulators such as Stonefish, providing a clear visualization layer
between the robot and the user.

---

## Project Capabilities

### Communication with ROS2
- Live subscription to ROS2 topics
- Visualization of robot motion and state data
- Support for camera streams and sensor outputs
- Flexible topic mapping for different robot setups

### 3D Environment Visualization
- Real-time display of robot position and orientation
- Motion updated using velocity and odometry information
- Interactive camera controls (rotate, zoom, pan)
- Clear 3D representation suitable for simulation analysis

---

## System Requirements

### Unity Side Dependencies

The following Unity packages are required for communication with ROS2:

- **ROS TCP Connector**
  - Enables network communication between Unity and ROS2
  - Source: https://github.com/Unity-Technologies/ROS-TCP-Connector

- **ROS Message Visualization Tools**
  - Used for decoding and displaying ROS messages inside Unity

---

### ROS2 Side Dependencies

To allow Unity to connect to ROS2, the following package must be running:

- **ROS TCP Endpoint**
  - Acts as a bridge between ROS2 nodes and Unity
  - Source: https://github.com/Unity-Technologies/ROS-TCP-Endpoint

---

## Configuration Guide

### Unity Setup

1. Open the project in Unity
2. Navigate to:
3. Configure the connection:
- ROS IP Address: `127.0.0.1` (for local testing)
- Port: `10000`
- Protocol: ROS2

4. Robot Coordinate Configuration:
- Enable **Unity coordinate mode** when using Unity-based simulations
- Disable it when using Stonefish or other external simulators

---

### ROS2 Setup

Ensure that the robot simulation or hardware is publishing the expected
topics. Topic remapping can be applied if naming differs between systems.

---

## Running the System

### 1. Start ROS TCP Server

Run the ROS TCP endpoint:

```bash
ros2 run ros_tcp_endpoint default_server_endpoint --ros-args \
-p ROS_IP:=127.0.0.1 \
-p ROS_TCP_PORT:=10001
Make sure the selected port is not already in use.''

# Start the Robot Simulation

Launch either:

A Stonefish underwater simulation

A Unity-based simulation

A real underwater robot (if available)

3. Launch the Unity Interface

Press Play inside Unity to start the GUI.

The interface will automatically:

Receive robot odometry

Update the 3D robot pose

Display sensor and camera data

Allow monitoring of active ROS2 topics

Academic Note

This project was prepared as part of a university assignment.
The repository structure and workflow are adapted for educational use.



Student: Mukesh
