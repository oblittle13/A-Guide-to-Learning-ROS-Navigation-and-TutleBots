Now we want to make sure that our local machine can communicate with the TurtleBot laptop. This is so we can run commands, and launch programs without having to be directly tied to the turtlebot (onyl virtually). [These steps were derived from here](http://wiki.ros.org/turtlebot/Tutorials/indigo/Network%20Configuration).

1. First things first, make sure both your local machine and the TurtleBot are connected to the internet. Otherwise, this step is impossible.
2. Now, on both machines we need to find out what their IP address is. To do this type 'hostname -I' into the command line.
3. These commands we need to execute on the TurtleBot laptop.
   - `echo export ROS_MASTER_URI=http://localhost:11311 >> ~/.bashrc`
   - `echo export ROS_HOSTNAME=IP_OF_TURTLEBOT >> ~/.bashrc`
4. Now we need to run these commands on your local machine.
   - `echo export ROS_MASTER_URI=http://IP_OF_TURTLEBOT:11311 >> ~/.bashrc`
   - `echo export ROS_HOSTNAME=IP_OF_PC >> ~/.bashrc`
5. Now, we need to make sure this worked. To do this, on your local machine open up a new terminal window and type `roscore`. This will get ROS running on your local machine. Open a new terminal window and type `rostopic list`. If you see "ERROR: Unable to communicate with master!", it either means you entered an IP address wrong, or you forgot to run `roscore`.
6. If the step above it done, on your local machine type `rostopic echo /diagnostics` into the command line. If you **don't** see an error, check that the ROS_HOSTNAME on the TurtleBot laptop is correct.
7. Now, **on both machines, completely close out the terminal, and start fresh. This will allow the terminal to catch up to all the changes we made to the bash files.**
8. If steps 5 and 6 were a success, we now know that the connect going from your local machine to the TurtleBot was a success. Now we want to check the connecting going in the opposite direction.On both machines we need to start `roscore`. 
   - If when you try to launch `roscore` nothing seems to happen. There's a good chance your IP has changed, especially on University/Company internet since they often will shuffle around IP addressed for security reasons. Try to verify that all your IP addressed from the steps above have not changed.
   - On your local machine type `rostopic pub -r10 /hello std_msgs/String "hello"` into the command line. Then, on the TurtleBot laptop type `rostopic echo /hello` into the command line. In a few seconds, you will see "hello" printed on the TurtleBot laptop.To stop this, press `crt-c'.
10. Finally, we want to install Chrony. This will allow the clocks on both machines to sink up. This step is imperative for everything to work nciely with eachother. To do this type `sudo apt-get install chrony`.
