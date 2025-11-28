# 3-dof-arm-Avni
Documents and instructions for 3 dof arm

Needed softwares

Ubuntu 24.04
Ros 2 Jazzy
Gazebo Harmonic
Python 3

How to Run?

arm3dof/
├── models/
│ └── arm3dof/
│ └── model.sdf
├── worlds/
│ └── arm_world.sdf
├── src/
│ └── move_demo.py
├── launch/
├── CMakeLists.txt
└── package.xml

1.Create workspace
2.Clone the repo
3. Compile

cd ~/arm_ws
colcon build
source install/setup.bash

RUN THE SIM

1.Terminal 

 In the path of the SDF file run
 gz sim arm.sdf

 2.Terminal

Run the bridge in the same path

ros2 run ros_gz_bridge parameter_bridge /arm/j1/cmd_pos@std_msgs/msg/Float64@gz.msgs.Double /arm/j2/cmd_pos@std_msgs/msg/Float64@gz.msgs.Double /arm/j3/cmd_pos@std_msgs/msg/Float64@gz.msgs.Double /joint_states@sensor_msgs/msg/JointState@gz.msgs.Model

3.Terminal

Run the python node in its path

ros2 run arm3dof move_demo.py







 



