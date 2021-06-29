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
Install Dependent ROS 1 Packages 
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
Install TurtleBot3 Packages 
```
$ sudo apt-get install ros-kinetic-dynamixel-sdk
$ sudo apt-get install ros-kinetic-turtlebot3-msgs
$ sudo apt-get install ros-kinetic-turtlebot3

```
**3. Enter these codes in the terminal to install Simulation packages**

Simulation Install 
```
$ cd ~/catkin_ws/src/
$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make

```
 
**4. Open a new terminal**

**5.  type in this command in the terminal**
```
$ source ~/catkin_ws/devel/setup.bash
```
**6. Run these commands in the terminal to launch the simulation world.**

||_. Launch Simulation World_
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

```
**7. Open a new terminal.**

**8.Type this to launch the SLAM Node.**

"Run SLAM Node"
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
**to run the SLAM Node and see the generated map by the Robot.**

**9. Open a new terminal again.**

**10. Run this command to be able to interact and control the robot**

 Run Teleoperation Node
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
**now you can start mapping**

**To save the map open a new terminal and type the following command**
```
$ rosrun map_server map_saver -f ~/map
```

**You will find the map in documents and here is picture of my map**
![map](https://user-images.githubusercontent.com/85397914/123870280-c9afbc00-d93a-11eb-8d31-b1d1c24edf1c.jpg)

**also a screenshot of what you should see while mapping **
![SharedScreenshot  map](https://user-images.githubusercontent.com/85397914/123870542-1eebcd80-d93b-11eb-89bd-8e4688974f0a.jpg)


For more information go to  [Robotis](https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/).
