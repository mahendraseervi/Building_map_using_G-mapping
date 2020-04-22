# Building_map_using_G-mapping
Implementing a gmapping ROS package which is based on the Grid-based FastSLAM algorithm to map an gazebo environment.

## Ros packages used:
1. turtlebot_gazebo
2. Gmapping
4. turlebot_teleop
5. rviz


## Steps to Launch:
### step 1 create the catkin_ws
```
$ mkdir -p /home/workspace/catkin_ws/src
$ cd /home/workspace/catkin_ws/src
$ catkin_init_workspace
$ cd ..
$ catkin_make
```

### Step 2 Perform a System Update/Upgrade
```
$ apt-get update
$ apt-get upgrade -y
```
### Step 3 Clone the Package in src
```
$ cd /home/workspace/catkin_ws/src
$ git clone https://github.com/mahendraseervi/Building_map_using_G-mapping.git
```
### Step 4 Build the Packages
```
$ catkin_make
$ source devel/setup.bash
```
### Step 5 Launch the myhouse gazebo world with turtlebot in it
```
$ roslaunch turtlebot_gazebo turtlebot_world.launch
```
### Step 6 run gmapping node present inside the gmapping package
```
$ rosrun gmapping slam_gmapping
```
### Step 7 Launch the rviz and save the required configuration
```
$ rosrun rviz rviz 
```
### Step 7 use the teleop_twist_keyboard to move the robot and create the map
```
$ rosrun teleop_twist_keyboard teleop_twist_keyboard.py 
```
Now, you should see Gazebo and rviz launching with robot inside it. Move aroud the robot inside gazebo world and create the map of the world

### Step 7 Save a map of the environment
```
$ cd /home/workspace/
$ rosrun map_server map_saver -f myMap
```

