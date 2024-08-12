# Mycobot 280 with ROS2 Humble, ROS2 control and MoveIt2

This description involves controlling a Mycobot 280 robot using ROS 2, MoveIt!, and Gazebo simulation. The system allows for sending desired poses to the robot, launching ROS 2 control simulations, and running the robot in a real environment.

## Features

- **Mycobot 280 Control**: Control the Mycobot 280 robot using ROS 2.
- **MoveIt! Integration**: Use MoveIt! for planning and executing robot trajectories.
- **ROS 2 Control**: Manage robot hardware interfaces and controllers using ROS 2 control.
- **Gazebo Simulation**: Simulate the robot in a virtual environment using Gazebo.

## Usage

### 1. Gazebo, ros2_control and moveit2

```bash
# Launch the Mycobot Gazebo simulation
ros2 launch mycobot_gazebo mycobot_280_arduino_bringup_ros2_control_classic_gazebo.launch.py

# Launch the simulation move group
ros2 launch mycobot_moveit_config move_group.launch.py
```

### 2. Launching real robot with control and moveit2

```bash
ros2 launch mycobot_280_description move_group.launch.py
```

### 3. Giving a Desired Pose

Listens to [X, Y, Z] topic and sends the desire pose to moveit2:

```bash
# Launch the MoveIt! test trajectory
ros2 launch moveit2_scripts test_trajectory.launch.py
```

# Experimental instructions

### 1. Lauch Slicer on Linux 

```bash
# Source ROS2 Humble
source /opt/ros/humble/setup.bash
# Launch Slicer
cd Slicer-build
./Slicer
```

### 2. Launch real robot with MoveIt2

```bash
ros2 launch mycobot_280_description move_group.launch.py
```


### 3. Merge Slicer and robot coordinate frames

Using the Moveit2 interface in rviz and fiducial registration wizard module in Slicer to combine the put everything in robot coordinate frame.

Set four fiducils points in Slicer at known locations and move the robot to each fiducial in real life in the order of the points and select place to in the registration wizard.

<img width="337" alt="image" src="https://github.com/user-attachments/assets/4bca73f0-4bd0-4ade-a5fc-a3594d40af51">




### 4. Start listening to Slicer



### 5. Start Slicer module



### 6. Experiment starts



