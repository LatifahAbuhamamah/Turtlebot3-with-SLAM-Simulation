# Turtlebot3-with-SLAM-Simulation
A step-by-step to simulating TurtleBot3 with Gazebo and using SLAM (Simultaneous Localization and Mapping) to create a map in ROS (Noetic).

**1. Install TurtleBot3 and Dependencies:**

   Install the TurtleBot3 packages and dependencies by following the official installation guide: [TurtleBot3 Installation](https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/)

**2. Install Simulation Packages:**

   We will need Gazebo and related simulation packages. Install them using the following command:

   ```bash
   sudo apt-get install ros-noetic-turtlebot3-gazebo ros-noetic-turtlebot3-slam
   ```

**3. Set Up Workspace:**

   If you don't have a ROS workspace, create one and navigate to the "src" directory:

   ```bash
   mkdir -p ~/catkin_ws/src
   cd ~/catkin_ws/src
   ```

**4. Clone the TurtleBot3 Simulation Repository:**

   Clone the TurtleBot3 simulation repository into workspace:

   ```bash
   git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
   ```

**5. Build Workspace:**

   Go back to the workspace root and build the workspace:

   ```bash
   cd ~/catkin_ws
   catkin_make
   source devel/setup.bash
   ```

**6. Launch Gazebo Simulation:**

   Launch the TurtleBot3 simulation in Gazebo:

   ```bash
   roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch
   ```

   This will open Gazebo with TurtleBot3 in an empty world.

**7. Launch SLAM Mapping:**

   Open a new terminal and launch the SLAM mapping node:

   ```bash
   roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
   ```

**8. Control the Robot:**

   To manually control the robot and navigate it in the environment, open another terminal and run the teleoperation node:

   ```bash
   roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
   ```

   Use the keys on your keyboard to control the robot's movement.


![Result](https://github.com/LatifahAbuhamamah/Turtlebot3-with-SLAM-Simulation/assets/139233344/232d08a9-be30-40dc-92d6-39e2d1f5b3f6)

   

**9. Save the Map:**

   After navigating the robot around the environment, the SLAM algorithm will create a map. Once you're satisfied with the coverage, save the map using:

   ```bash
   rosrun map_server map_saver -f ~/map
   ```



