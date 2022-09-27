Now comes the important part, actually connecting to the TurtleBot. I followed [this tutorial](http://wiki.ros.org/turtlebot_bringup/Tutorials/indigo/TurtleBot%20Bringup). A few things weren't the greatest about it. So I've altered a few things, to make things easier for beginners to understand.
 
 1. First things first, we want to make sure our setup.bash is sourced. Essentially what this means is that every time we open up a new terminal window that our ros packages are loaded. (Do this on both your local machine, and the TurtleBot laptop. Note: my TurtleBot laptop is running ROS melodic, so i swapped the distros in the command)
   - To do this, open up a terminal window and type `source /opt/ros/noetic/setup.bash`. 
   - Alternatively, you could add this line in your ~/.bashrc file, just before any import or export commands.
 2. Now, we need two terminal windows that are both SSH'ed into the TurtleBot laptop. We need to do a special kind of SSH so that any graphical pop-ups or things that are opened, end up on your local machine, rather than on the TurtleBot laptop. To do this type `ssh -Y <name>@<laptopip>`
   - In the first window we need to run the following command: `roslaunch turtlebot_bringup minimal.launch --screen`
   - In the second window we need to run on of two sets of commands:
     - If you have a Kobuki base to your TurtleBot:
       - rqt -s kobuki_dashboard
       - If the command above fails, install the Kobuki dashboard with `sudo apt-get install ros-indigo-kobuki-dashboard` (if there is an issue with it, run this command afterwards `rqt --force-discovery`, then retry `rqt -s kobuki_dashboard`)
       - In a few seconds you'll see a window pop up on your screen, it's just there to display some information for you.
      - If you have a Create base then run this `roslaunch turtlebot_dashboard turtlebot_dashboard.launch`
3. If everything went smoothly, we are now ready to move onto actually doing things with the TurtleBot. If it didn't go well, and some things arent working, try a google search.
     
