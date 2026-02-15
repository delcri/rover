
## 📄 README.md – ROS 2 Rover (Control & Simulation)

```markdown
# ROS 2 Rover – Mobile Robotics Platform 🚀🤖

This repository contains the development of a **mobile rover built with ROS 2 Humble**, focused on **motion control, teleoperation, and simulation**, without the integration of physical or virtual sensors.

The project was designed as a **clean and extensible robotic base**, suitable for testing control strategies, ROS 2 architecture, and simulation workflows.

---

## 🧠 Project Overview

This rover implements:

- Motion control using ROS 2
- Manual teleoperation
- Simulation in **RViz** and **Gazebo**
- Modular ROS 2 node architecture
- Standard ROS 2 topic communication (`/cmd_vel`, `/odom`, `/tf`)
- Clear separation between control, simulation, and visualization layers

⚠️ Note:  
This project **does not include sensors** (Lidar, camera, IMU, etc.).  
Its focus is strictly on **locomotion, control, and simulation of a mobile robot**.

---

## 🎯 Project Goals

- Apply ROS 2 Humble to a realistic mobile robot platform
- Design a solid and scalable ROS 2 architecture
- Validate rover motion and control in simulation before hardware deployment
- Serve as a base platform for future navigation or perception projects

---

## 📦 Key Features

### 🤖 Rover Control

- Velocity command interface using `geometry_msgs/Twist`
- Differential drive motion control
- Manual teleoperation
- Compatible with both simulation and real hardware setups

### 🛠 Simulation

Fully compatible with:

- **Gazebo** – physics-based rover simulation
- **RViz** – visualization of:
  - Robot model
  - Odometry
  - TF transformations
  - Motion trajectory

Simulation allows validating the rover’s kinematic behavior without physical hardware.

---

## 🧩 Repository Structure

```

rover/
│
├── launch/        # ROS 2 launch files
├── nodes/         # Control and teleoperation nodes
├── config/        # System configuration parameters
├── gazebo/        # Simulation worlds and robot models
├── rviz/          # RViz visualization configs
├── src/           # Main source code
└── README.md

````

---

## 🚀 Installation

### Requirements

- Ubuntu 22.04
- ROS 2 Humble
- Colcon build system

---

### Clone and build

```bash
source /opt/ros/humble/setup.bash
cd ~/ros2_ws/src
git clone https://github.com/delcri/rover.git
cd ..
colcon build --symlink-install
source install/setup.bash
````

---

## ▶️ Running the Simulation

### Launch Gazebo

```bash
ros2 launch rover gazebo_launch.py
```

### Visualize in RViz

```bash
rviz2 -d rviz/rover.rviz
```

---

## ▶️ Teleoperation

```bash
ros2 launch rover teleop_launch.py
```

This allows manual control of the rover’s movement.

---

## 📡 ROS 2 Topics

| Topic           | Type                   | Description           |
| --------------- | ---------------------- | --------------------- |
| `/cmd_vel`      | geometry_msgs/Twist    | Velocity commands     |
| `/odom`         | nav_msgs/Odometry      | Robot odometry        |
| `/tf`           | tf2_msgs/TFMessage     | Coordinate transforms |
| `/joint_states` | sensor_msgs/JointState | Model joint states    |

---

## 🧠 What This Project Demonstrates

✔️ Solid ROS 2 fundamentals
✔️ Clean node architecture
✔️ Gazebo + RViz integration
✔️ Mobile robot control
✔️ Launch system and workspace organization
✔️ Scalable base for more advanced robotics projects

---

## 🚧 Future Improvements

* Sensor integration
* Autonomous navigation (Nav2)
* SLAM
* Advanced control strategies
* Path planning

