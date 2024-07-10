# Adding IAS Lab Environment to Gazebo
## 1. Download Needed File
Download the [`ias.zip`](ias.zip) File

Open a new terminal using `CTRL` + `ALT` + `T` or from the applications pane and run this command
```bash
sudo apt install unzip
cd ~/Downloads
unzip ias.zip -d ~/Downloads
```

## 2. Move the Files
Run the following Commands
```bash
mkdir ~/.gazebo/models/IAS
mkdir ~/.gazebo/models/IAS/meshes
cd ~/Downloads
mv model.config model.sdf ~/.gazebo/models/IAS
mv model.dae Image_0.jpg ~/.gazebo/models/IAS/meshes
mv turtlebot3_ias.launch turtlebot3_ias_gripper.launch ~/catkin_ws/src/turtlebot3_simulations/turtlebot3_gazebo/launch
mv IAS.world ias_empty.world ~/catkin_ws/src/turtlebot3_simulations/turtlebot3_gazebo/worlds
mv turtlebot3_manipulation_gazebo_ias.launch ~/catkin_ws/src/turtlebot3_manipulation_simulations/turtlebot3_manipulation_gazebo/launch
```

## 3. Run the Simulation
Running it with manipulator
```bash
roslaunch turtlebot3_manipulation_gazebo turtlebot3_manipulation_gazebo_ias.launch
```

Running it without manipulator
```bash
roslaunch turtlebot3_gazebo turtlebot3_ias.launch
```
