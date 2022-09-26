This step needs to be done on both the device connected to the TurtleBot, and your local machine. There are alot of different steps to do depending on which. As per usual, a more indepth guide can be found [here](http://wiki.ros.org/turtlebot/Tutorials/indigo/Turtlebot%20Installation). For my case (and should be yours as well since you are following this tutorial) we only need the commands below `Source Installation` on the guide above. I'll give you all the commands below.

Note: Once again, all of this is to be done in the Terminal.

1. Open the Terminal and type in the following commands:
   - `sudo apt-get install python3-rosdep python3-wstool ros-noetic-ros`
   - `rosdep update`
   - `mkdir ~/rocon`
     - I've decided to call the folder in which I will be working "rocon", this is simply becaus it's what the tutorial told me. You can name this anything you'd like, as long as you remember what it is, and put that in rather than "rocon" if you see it in a command.
   - Now, what we want to do is run [this make file](../"Chapter 0 - Setup"/makefile) inside you folder. Simply download it, move it into your folder, then navigate to this folder in your command line, and type 'make'. This will automatically download all the required libraries into this folder.
