# turtlebot3
turtlebot3

```
mkdir -p ~/catkin_ws
cd ~/catkin_ws/
catkin_make --source $HOME/catkin_ws
source devel/setup.bash
```

### dependencies:

```
git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
git clone --recursive https://github.com/saimouli/frontier_exploration_turtlebot.git
```

```
sudo apt-get install ros-kinetic-map-server 
sudo apt-get install ros-kinetic-move-base
sudo apt-get install ros-kinetic-amcl 
sudo apt-get install ros-kinetic-cartographer-ros
https://google-cartographer-ros.readthedocs.io/en/latest/compilation.html
sudo apt-get install ros-kinetic-frontier-exploration ros-kinetic-navigation-stage
```

### catkin_make:

```
catkin_make --source $HOME/catkin_ws
source devel/setup.bash
```

### Bashrc:

```
source /opt/ros/kinetic/setup.bash
source $HOME/turtlebot3/devel/setup.bash
export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:$HOME/turtlebot3/src/turtlebot3_simulations/turtlebot3_gazebo/models
export TURTLEBOT3_MODEL=burger
export TURTLEBOT3_MODEL=waffle
export TURTLEBOT3_MODEL=waffle_pi
```

### SLAM:

```
$ roslaunch turtlebot3_gazebo turtlebot3_house.launch
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=frontier_exploration
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
$ roslaunch turtlebot3_gazebo turtlebot3_simulation.launch
$ rosrun map_server map_saver -f /home/arslan/Turtlebot3/maps
$ rosrun map_server map_saver -f ~/map
```

### Frointer-exploration:

```
$ roslaunch frontier_explorer_turtlebot demo.launch
$ rosrun map_server map_saver -f my_map
```

### Navigation:

```
$ roslaunch turtlebot3_gazebo turtlebot3_house.launch
$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
```
