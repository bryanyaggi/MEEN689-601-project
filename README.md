# MEEN 689-601 Project  

## Docker Setup  
1. `cd nmpc_project/docker`  
2. Build image: `./build.sh`  
3. Start container:  
    1. Edit project path on line 15 of `run.sh`  
    2. `./run.sh`  
4. Get shell session in container: `./shell.sh`  
5. Build ROS workspace from inside container: `./project/nmpc_racing/docker/catkin_ws.sh`  

## Build Baseline NMPC Optimizer  
_Must build from container shell session_  
`python3 project/nmpc_racing/optimization/PANOC_DYNAMIC_MOTOR_MODEL/all_wheel_drive_PANOC_DINAMYC_motor_model.py`  

## Build Kinematic NMPC Optimizer  
_Must build from container shell session_  
`python3 project/nmpc_racing/optimization/kinematic_model/kinematic_model.py`  

## Run Controller in Simulation  
_Commands must be run from container shell session_  
In first terminal:  
    1. Source ROS workspace: `source catkin_ws/devel/setup.bash`  
    2. Launch simulation: `roslaunch f1tenth-sim sim.launch`  
In second terminal:  
    1. Source ROS workspace  
    2. If desired, edit track and controller at bottom of `nmpc_racing/scripts/node.py`  
    3. Run controller: `rosrun f1tenth-sim node.py`  
