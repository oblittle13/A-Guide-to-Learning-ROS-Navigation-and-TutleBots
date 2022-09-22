Now we need to install ROS on our local system. There are severl steps here, so for an indepth guide [click here](http://wiki.ros.org/noetic/Installation/Ubuntu). My tutorial will be a little more bare bones compared to this one

Note: We will be installing everything by using the command line inside the terminal.
Note: We want to install this on both your local machine, and the workstation attatched to the TurtleBot
Note: During this installation, multiple times it will ask you if you are sure you want to install things. Just type `y` in the terminal.

1. Firstly, when installing new packages its alawys do practice to update what we already have installed. type `sudo apt-get update` into the terminal.
2. Next, we want to install a few things, type all of these into the terminal
   - `sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'`
   - `sudo apt install curl`
   - `curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -`
   - `sudo apt update`
   - `sudo apt install ros-noetic-desktop-full`
   - `source /opt/ros/noetic/setup.bash`
   - `echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc`
   - `source ~/.bashrc`
   - `sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential`
   - `sudo apt install python3-rosdep`
   - `sudo rosdep init`
   - `rosdep update`
3. It's now recommended that that you try to do [one of these](http://wiki.ros.org/ROS/Tutorials) ROS tutorials to make sure your install went smoothly.
