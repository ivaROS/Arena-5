# Arena-Rosnav (ivaROS custom-humble)

A modular ROS 2 (Humble) platform for researching and benchmarking autonomous robot navigation in 2D and 3D simulated environments. It supports classical planners (Nav2), deep-RL planners ([rosnav_rl](https://github.com/Arena-Rosnav/rosnav-rl)), and a variety of simulators (Gazebo, Isaac Sim).

---

## Installation
## make sure 'which ros2' command doesn't output anything. If it does, unlink/unsource your ros2 or uninstall.
## if a package fails to build during installation, use the command "rm -rf build/<failed_package> install/<failed_package>" and then rerun the bash install.sh command. if that's not working, you can source arena and then rebuild there after removing the respective build and install package folders. 
```sh
sudo apt update
sudo apt install software-properties-common
curl https://raw.githubusercontent.com/ivaROS/Arena-5/custom-humble/install.sh > install.sh
bash install.sh

cd ~/arena5_ws # replace with your actual workspace path
source arena
arena update
arena build
arena feature gazebo install # optional
arena feature isaac install # optional
arena feature training install # optional
```

## Usage

```sh
cd ~/arena5_ws # replace with your actual workspace path
source arena
arena launch sim:=gazebo                         # default — Gazebo simulator
arena launch sim:=isaac                          # Isaac Sim
arena launch local_planner:=rosnav_rl agent_name:=<your_agent>  # DRL planner
arena launch sim:=gazebo local_planner:=rosnav_rl env_n:=2 train_config:=<path to config.yaml> # DRL training 
```

> **DRL quick-start**: place your trained agent folder inside `Arena/arena_training/agents/<agent_name>/` (must contain `training_config.yaml` and `best_model.zip`), then launch with `local_planner:=rosnav_rl agent_name:=<your_agent>`. Refer to the [arena_training README](arena_training/README.md) for training instructions.
