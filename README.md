# dynamixel_pantilt_description

This package intents to use two dynamixel motors as pantilt. It contains the URDF and launch file example.

## Installation

Select a ROS workspace

```bash
cd ~/catkin_ws/src
```

Install this repository

```bash
git clone https://github.com/RobotnikAutomation/dynamixel_pantilt_description.git
```

Install dynamixel dependencies

```bash
git clone https://github.com/RobotnikAutomation/dynamixel_workbench_ros_control.git
git clone https://github.com/RobotnikAutomation/dynamixel-workbench.git
```

Install ROS dependencies

```bash
cd ~/catkin_ws
rosdep update
rosdep install --from-paths src --ignore-src -r -y
```
Build and source the workspace

```bash
cd ~/catkin_ws
catkin build
source devel/setup.bash
```

## Bringup

Launch the pan tilt

```bash
roslaunch dynamixel_pantilt_description pantilt_control.launch
```

Send command to the pan and tilt:

```bash
rostopic pub /robot/dynamixel_pan_controller/command std_msgs/Float64 "data: 0.7"
```

```bash
rostopic pub /robot/dynamixel_tilt_controller/command std_msgs/Float64 "data: 0.3"
```