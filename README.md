# gnc: An example project of BridgePoint for controlling quad copter for APRIS Robot Challange

## How to run

1. Install AirSim and ArduPilot SITL for Ubuntu on Windows Subsystem for Linux (WSL 1)

* https://github.com/hisazumi/aprisrc-sitl/tree/forairsim

2. Download this project in catkin_ws/src in the conatiner
```
cd ~/catkin_ws/src
git clone https://github.com/hisazumi/gnc.git
```

3. Import to your bridgepoint workspace

* launch bridgepoint (just type 'bridgepoint' on termianl in the container)
* File menu -> Import -> General/Existing Project into Workspace -> Select root directory
* and select imported directory (it should be ~/catkin_ws/src/gnc)
* Build on BridgePoint (Ctrl+B or Project menu -> Build all)

4. Run in terminal

* Before executing gnc, run Airsim, ArduCopter SITL, and apm accroding to README.md of the installation instruction.
```
rosrun gnc ctrl
```
