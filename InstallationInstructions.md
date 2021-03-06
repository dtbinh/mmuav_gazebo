# Installation Instructions

**Important Notice**

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) If you cloned this repository before 16. May, 2018. please do the following steps:

```
cd ~/catkin_ws/src
sudo rm -r rotors_simulator
sudo rm -r mav_comm
```
Next, clone the repository as described in **Install required simulation packages** below.


## Configure workspace

This instructions consider you have [ROS](http://wiki.ros.org/kinetic/Installation/Ubuntu) installed. Following dependencies have to be installed before configuring the workspace:

```sudo apt-get install python-wstool python-catkin-tools ros-kinetic-octomap-ros ros-kinetic-dynamic-edt-3d libssh2-1-dev unzip libyaml-cpp0.5v5 libblas-dev liblapack-dev```

Next, initialize workspace using catkin tools:

```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin init
catkin config --extend /opt/ros/kinetic
catkin config --cmake-args -DCMAKE_BUILD_TYPE=Release
cd ~/catkin_ws
catkin build
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

## Install required simulation packages

If you don't have git you can install it with:
```sudo apt-get install git```

Next, clone and checkout following packages in `src` folder:

```
cd ~/catkin_ws/src
git clone https://github.com/larics/rotors_simulator
cd rotors_simulator
git checkout larics_master
cd ~/catkin_ws/src
git clone https://github.com/larics/mav_comm
cd mav_comm
git checkout larics_master
```


Before you build, install following dependencies:

```
sudo apt-get install libopencv-dev
sudo apt-get install ros-kinetic-joy ros-kinetic-octomap-ros ros-kinetic-mavlink python-wstool python-catkin-tools protobuf-compiler libgoogle-glog-dev ros-kinetic-control-toolbox ros-kinetic-mavros ros-kinetic-effort-controllers ros-kinetic-position-controllers ros-kinetic-robot-controllers ros-kinetic-joint-state-controller ros-kinetic-controller-manager ros-kinetic-gazebo-ros-control ros-kinetic-hector-gazebo-plugins ros-kinetic-xacro ros-kinetic-robot-state-publisher
catkin build
```

Finally, clone mmuav_gazebo repository:

```
cd ~/catkin_ws/src
git clone https://github.com/larics/mmuav_gazebo.git
catkin build
```
