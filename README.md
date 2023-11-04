# gnc: A project of BridgePoint for controlling multi-copter (quad copter)

This project for APRIS Robot Challange and enPiT summer school.


## How to run

You need to setup a developing environment.

https://github.com/hisazumi/aprisrc-sitl/tree/forairsim

After setup the environment, clone this repository to `~/catkin_ws/src`.  
You can backup (means moving to another directory) the already existing gnc if you need it. Also you can delete the gnc.

When cloning this repository, you must rename this repository to `gnc`.

```
git clone https://github.com/multi-copter-system/multi-copter-gnc.git gnc
```

Next,

- Launch bridgepoint (ex. `~/BridgePoint/bridgepoint`)
- File menu (top left on the window) -> Import -> General/Existing Project into Workspace -> Select root directory
- Select imported directory (it should be `~/catkin_ws/src/gnc`)
- Build on BridgePoint (Project menu (top on the window) -> Build all)

Then, you must run the below command:

```
source ~/catkin_ws/devel/setup.bash
```

Finally, executing gnc.

Order:  
run ArduCopter SITL ->  launch AirSim -> `roslaunch iq_sim apm.launch` -> You need wait to see a message such as `AP: EKF2 IMU0 is using GPS` -> `rosrun gnc ctrl`

```
sim_vehicle.py -v ArduCopter -f airsim-copter
```

```
roslaunch iq_sim apm.launch
```

```
rosrun gnc ctrl
```

And you can control multi-copter using ROS topic.

```
rostopic pub /gnc_node/cmd std_msgs/String "data: 'arming'"
```

Command list:

- `ready`
- `arming`
- `halt`
- `begin_move`
- `begin_return`

For more information about controlling multi-copter using ROS topic:

https://github.com/multi-copter-system/multi-copter-ctrl