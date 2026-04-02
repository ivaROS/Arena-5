<<<<<<< Updated upstream
=======
# Arena-Rosnav (ivaROS custom-humble)

A modular ROS 2 (Humble) platform for researching and benchmarking autonomous robot navigation in 2D and 3D simulated environments. It supports classical planners (Nav2), deep-RL planners ([rosnav_rl](https://github.com/Arena-Rosnav/rosnav-rl)), and a variety of simulators (Gazebo, Isaac Sim).

---

>>>>>>> Stashed changes
## Installation

```sh
curl https://raw.githubusercontent.com/ivaROS/Arena-5/custom-humble/install.sh > install.sh
bash install.sh

cd ~/arena5_ws # replace with your actual workspace path
source arena
arena update
arena build
arena feature gazebo install # optional
arena feature isaac install # optional
```

## Usage

```sh
cd ~/arena5_ws # replace with your actual workspace path
source arena
arena launch sim:=isaac # add ros2 launch args as needed
```
<<<<<<< Updated upstream
=======

> **DRL quick-start**: place your trained agent folder inside `Arena/arena_training/agents/<agent_name>/` (must contain `training_config.yaml` and `best_model.zip`), then launch with `local_planner:=rosnav_rl agent_name:=<your_agent>`. Refer to the [arena_training README](arena_training/README.md) for training instructions.
>>>>>>> Stashed changes
