# Controlling the robot arm by joint_state_publisher Moveit and kinematics
#### First, you must run ROS Noetic by sourcing the setup file.

```
source /opt/ros/noetic/setup.bash
```
#### Let's create and build a catkin workspace:

```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
```
#### Now, let's execute our source file :
```
source devel/setup.bash
```

### To install the arduino_robot_arm package, you can use the following steps:
Step 1: Update the Package List

First, make sure your package list is up to date:
```
sudo apt update
```
#### Now add the “arduino_robot_arm” package to “src” folder

```
cd ~/catkin_ws/src
sudo apt install git
git clone https://github.com/smart-methods/arduino_robot_arm 
```
#### Install all the dependencies

```
cd ~/catkin_ws
	rosdep install --from-paths src --ignore-src -r -y
	sudo apt-get install ros-noetic-moveit
	sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
  sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
  sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
```

### Compile the package ```catkin_make```

##### To control the motors, you can use the following command:

```
roslaunch robot_arm_pkg check_motors.launch
```

This command will launch the check_motors.launch file from the robot_arm_pkg package, allowing you to control the motors of the robot arm.

`![12e](https://github.com/user-attachments/assets/83543639-f350-4b03-a122-8660e3009d6c)

#### Controlling the motors joint_state_publisher

this will launch the ```rqt_graph``` visualization tool as it appears
![Screenshot at 2024-08-10 16-02-40](https://github.com/user-attachments/assets/39546170-b0f5-4b57-8d9f-d7f12855ac12)

By using this command, you can monitor the real-time state of the robot's joints and verify their values.
```
rostopic echo /joint_states
```
![asaa](https://github.com/user-attachments/assets/d6d2616d-fccd-484e-ba08-1c15744d7fee)

Executing this command ```roslaunch moveit_pkg demo.launch```   will help you visualize or test the motion planning capabilities and other features provided by MoveIt! for your robot.
![Screenshot at 2024-08-10 17-37-18](https://github.com/user-attachments/assets/d6b52fe4-490a-4f26-beae-0c68eed711d1)



























