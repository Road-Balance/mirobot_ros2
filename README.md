# mirobot_ros2
WLKATA Mirobot ROS 2 Pkgs

## Package build Example

1. create ros2 workspace

```bash
mkdir -p ~/mirobot_ros2_ws/src
cd ~/mirobot_ros2_ws
colcon build --symlink-install
```

2. clone and build serial package

```bash
cd ~/mirobot_ros2_ws/src
git clone https://github.com/RoverRobotics-forks/serial-ros2.git
cd ../
colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release serial
```

3. build this repo

```bash
cd ~/mirobot_ros2_ws
source ./install/setup.bash
cd src
git clone https://github.com/Road-Balance/mirobot_ros2.git
cd ../
colcon build --symlink-install --packages-select mirobot_description
source ./install/setup.bash
```

---

## Usage

* rviz control

```
sudo chmod 777 /dev/ttyUSB0
ros2 launch mirobot_description mirobot_rviz_control.launch.py 
```

* isaac sim control

```
sudo chmod 777 /dev/ttyUSB0
ros2 run mirobot_description mirobot_gcode_writer 
ros2 launch mirobot_description mirobot_rviz_control.launch.py 
```
