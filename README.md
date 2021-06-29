# Turtlebot3-
# These will be the steps to install the tools needed for simulating, mapping, and controlling a turtlebot robot.


**1.Make sure you already have a running VM with ubuntu 18.04 OS, and already installed ROS Melodic inside it.**

**2.type in the commands down below in the terminal**

Install ROS 1 
 ```
$ sudo apt-get update
$ sudo apt-get upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh
$ chmod 755 ./install_ros_kinetic.sh 
$ bash ./install_ros_kinetic.sh
 ```
||_Install Dependent ROS 1 Packages ._
```
 $ sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy \
  ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc \
  ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan \
  ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python \
  ros-kinetic-rosserial-server ros-kinetic-rosserial-client \
  ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server \
  ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro \
  ros-kinetic-compressed-image-transport ros-kinetic-rqt* \
  ros-kinetic-gmapping ros-kinetic-navigation ros-kinetic-interactive-markers
```
||_Install TurtleBot3 Packages ._
```
$ sudo apt-get install ros-kinetic-dynamixel-sdk
$ sudo apt-get install ros-kinetic-turtlebot3-msgs
$ sudo apt-get install ros-kinetic-turtlebot3

```
**3. Enter these codes in the terminal to install Simulation packages**

||_Simulation Install ._
```
$ cd ~/catkin_ws/src/
$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make

```
 
**4. Make sure to  make a new terminal after the 3rd step**

**5. After you are done type in this command in the terminal**
```
$ source ~/catkin_ws/devel/setup.bash
```
**6. Run these commands in the terminal to launch the simulation world.**

||_. Launch Simulation World_
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

```


**7. Run these commands in the terminal to launch the SLAM Node.**

||_6. 2. 2. "Run SLAM Node"_
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
**to run the SLAM Node and see the generated map by the Robot.**

**8. Run this command to be able to interact and control the robot**

||_6. 2. 3. Run Teleoperation Node_
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
**After you run the 2 codes Now you should be able to control the robot using the keys WASDX to roam around the gazebo simulated map.**

**9. After you are done exploring the map with your robot you should save the map using (Ctrl + Alt + T).**

**You are done.**

For more information make sure to visit this website from which i took these steps [Robotis](https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/).
