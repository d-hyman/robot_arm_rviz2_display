## How to Run

**Prerequisites:** Ubuntu (or another Linux distro) with ROS 2 installed and sourced.

1. **Install ROS 2** (if not already installed)  
   Follow the official instructions for your distro: https://docs.ros.org/en/humble/Installation.html

2. **Source your ROS 2 installation** (add this to `~/.bashrc` to avoid repeating it every terminal session)
```bash
   source /opt/ros/<your-ros-distro>/setup.bash
```

3. **Create a workspace** (skip if you already have one)
```bash
   mkdir -p ~/ros2_ws/src
   cd ~/ros2_ws/src
```

4. **Clone or copy this package into the workspace's `src` directory**
```bash
   git clone <repo-url> robot_arm_assem_v5
```

5. **Install dependencies** (from the workspace root)
```bash
   cd ~/ros2_ws
   rosdep install --from-paths src --ignore-src -r -y
```

6. **Build the package**
```bash
   colcon build --packages-select robot_arm_assem_v5
```

7. **Source the overlay**
```bash
   source install/setup.bash
```

8. **Launch**
```bash
   ros2 launch robot_arm_assem_v5 display.launch.py
```

> RViz2 will open with the robot model loaded. If the display is empty, set **Fixed Frame** (top-left panel) to `base_link`.

<img width="1918" height="1027" alt="image" src="https://github.com/user-attachments/assets/97f8afee-b45d-4b1d-b541-b873f5d4e4db" />
