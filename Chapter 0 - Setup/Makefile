all: ./src/turtlebot ./src/turtlebot_apps ./src/turtlebot_msgs ./src/turtlebot_simulator ./src/turtlebot_rviz_launchers ./src/kobuki_msgs ./src/kobuki_gazebo_plugins ./src/kobuki_driver ./src/kobuki_description ./src/kobuki_node ./src/kobuki_keyop ./src/kobuki_safety_controller ./src/kobuki_bumper2pc ./src/openni2_camera ./src/rgbd_launch ./src/slam_gmapping ./src/move_base ./src/yocs_cmd_vel_mux ./src/yocs_controllers ./src/yocs_velocity_smoother ./src/depthimage_to_laserscan ./src/ecl_core ./src/ecl_lite ./src/ecl_mobile_robot ./src/ecl_tools

./src/turtlebot:
	git clone https://github.com/turtlebot/turtlebot.git $@

./src/turtlebot_apps:
	git clone https://github.com/turtlebot/turtlebot_apps.git $@

./src/turtlebot_msgs:
	git clone https://github.com/turtlebot/turtlebot_msgs.git $@

./src/turtlebot_simulator:
	git clone https://github.com/turtlebot/turtlebot_simulator.git $@

./src/turtlebot_rviz_launchers:
	git clone https://github.com/turtlebot/turtlebot_interactions.git ./src/turtlebot_interactions
	mv ./src/turtlebot_interactions/turtlebot_rviz_launchers ./src
	rm -rf ./src/turtlebot_interactions

./src/kobuki_msgs:
	git clone https://github.com/yujinrobot/kobuki_msgs.git $@

./src/kobuki_gazebo_plugins:
	git clone --single-branch https://github.com/yujinrobot/kobuki_desktop.git ./src/kobuki_desktop
	mv ./src/kobuki_desktop/kobuki_gazebo_plugins ./src
	rm -rf ./src/kobuki_desktop

./src/kobuki_driver:
	git clone --single-branch https://github.com/yujinrobot/kobuki_core.git ./src/kobuki_core
	mv ./src/kobuki_core/kobuki_driver ./src
	rm -rf ./src/kobuki_core

./src/kobuki_description: .kobuki
	[[ -d $@ ]] && echo "Exists: $@" || echo "Missing: $@"

./src/kobuki_node: .kobuki
	[[ -d $@ ]] && echo "Exists: $@" || echo "Missing: $@"

./src/kobuki_keyop: .kobuki
	[[ -d $@ ]] && echo "Exists: $@" || echo "Missing: $@"

./src/kobuki_safety_controller: .kobuki
	[[ -d $@ ]] && echo "Exists: $@" || echo "Missing: $@"

./src/kobuki_bumper2pc: .kobuki
	[[ -d $@ ]] && echo "Exists: $@" || echo "Missing: $@"

.kobuki:
	git clone --single-branch https://github.com/yujinrobot/kobuki.git ./src/kobuki
	mv ./src/kobuki/kobuki_description ./src/kobuki/kobuki_node ./src/kobuki/kobuki_keyop ./src/kobuki/kobuki_safety_controller ./src/kobuki/kobuki_bumper2pc ./src
	rm -rf ./src/kobuki
	touch $@

./src/openni2_camera:
	git clone --single-branch https://github.com/ros-drivers/openni2_camera.git $@

./src/rgbd_launch:
	git clone --single-branch https://github.com/ros-drivers/rgbd_launch.git $@

./src/slam_gmapping:
	git clone --single-branch https://github.com/ros-perception/slam_gmapping.git $@

./src/move_base:
	git clone --single-branch https://github.com/ros-planning/navigation.git ./src/navigation
	mv ./src/navigation/move_base ./src
	rm -rf ./src/navigation

./src/yocs_cmd_vel_mux: .yocs
	[[ -d $@ ]] && echo "Exists: $@" || echo "Missing: $@"

./src/yocs_controllers: .yocs
	[[ -d $@ ]] && echo "Exists: $@" || echo "Missing: $@"

./src/yocs_velocity_smoother: .yocs
	[[ -d $@ ]] && echo "Exists: $@" || echo "Missing: $@"

.yocs:
	git clone https://github.com/yujinrobot/yujin_ocs.git ./src/yujin_ocs
	mv ./src/yujin_ocs/yocs_cmd_vel_mux ./src/yujin_ocs/yocs_controllers ./src/yujin_ocs/yocs_velocity_smoother ./src
	rm -rf ./src/yujin_ocs
	touch $@

./src/depthimage_to_laserscan:
	git clone https://github.com/ros-perception/depthimage_to_laserscan.git $@

./src/ecl_core:
	git clone https://github.com/stonier/ecl_core.git --branch release/0.62-noetic $@

./src/ecl_lite:
	git clone https://github.com/stonier/ecl_lite.git --branch release/0.61-noetic $@

./src/ecl_tools:
	git clone https://github.com/stonier/ecl_tools.git --branch release/0.61-noetic $@

./src/ecl_mobile_robot:
	git clone https://github.com/stonier/ecl_navigation.git --branch release/0.60-noetic ./src/ecl_navigation
	mv ./src/ecl_navigation/ecl_mobile_robot ./src
	rm -rf ./src/ecl_navigation

deps:
	sudo apt-get install -y ros-noetic-joy libftdi-dev ros-noetic-openslam-gmapping ros-noetic-base-local-planner ros-noetic-clear-costmap-recovery ros-noetic-move-base-msgs ros-noetic-navfn ros-noetic-rotate-recovery xsltproc ros-noetic-map-server ros-noetic-amcl ros-noetic-dwa-local-planner ros-noetic-rosbridge-* ros-noetic-ecl-console ros-noetic-ecl-command-line ros-noetic-ecl-converters ros-noetic-ecl-devices ros-noetic-ecl-geometry ros-noetic-ecl-mobile-robot ros-noetic-ecl-sigslots ros-noetic-ecl-time python3-empy ros-noetic-ddynamic-reconfigure ros-noetic-teb-local-planner libignition-common3-graphics
