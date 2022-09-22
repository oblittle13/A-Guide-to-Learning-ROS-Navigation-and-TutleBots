This step needs to be done on both the device connected to the TurtleBot, and your local machine. There are alot of different steps to do depending on which. As per usual, a more indepth guide can be found [here](http://wiki.ros.org/turtlebot/Tutorials/indigo/Turtlebot%20Installation). For my case (and should be yours as well since you are following this tutorial) we only need the commands below `Source Installation` on the guide above. I'll give you all the commands below.

Note: Once again, all of this is to be done in the Terminal.

1. Open the Terminal and type in the following commands:
   - `sudo apt-get install python3-rosdep python3-wstool ros-noetic-ros`
   - `rosdep update`
   - `mkdir ~/rocon`
