# ros_edx


## Week1

Read a ultrasound sensor connected to an arduino board (see [here](https://github.com/jcorredorc/udemy_ros_beginners#arduino)). 


```
$roslaunch udemy_ros_beginners arduino_hcsr04.launch
```

Then publish the data in the custom message `SensorInformation.msg`

This script `sensor_info_publisher.py` is modified from the course objective, it reads the real sensor and publishes the data in the message `SensorInformation.msg`


```
$rosrun ros_edx sensor_info_publisher.py
```

### Assignments

1a. this script subscribe to `/sensor_info` and check if the data is less than 0.1.

```
$rosrun ros_edx week1_assignment1_part1.py 
```

1b. Creates a custom message

```
$ rosmsg show ros_edx/BoxHeightInformation 
float64 box_height
```

1c. Creates a node with a publisher and subscriber

```
$ rosrun ros_edx sensor_info_publisher.py
$ rosrun ros_edx week1_assignment1_part1.py
$ rosrun ros_edx week1_assignment1_part3.py
```

## Week2

Follow the next ROS tutorials:

* [Building a Visual Robot Model with URDF from Scratch](http://wiki.ros.org/urdf/Tutorials/Building%20a%20Visual%20Robot%20Model%20with%20URDF%20from%20Scratch)

* [Building a Movable Robot Model with URDF](http://wiki.ros.org/urdf/Tutorials/Building%20a%20Movable%20Robot%20Model%20with%20URDF)

* [Using Xacro to Clean Up a URDF File](http://wiki.ros.org/urdf/Tutorials/Using%20Xacro%20to%20Clean%20Up%20a%20URDF%20File)

see [join element](http://wiki.ros.org/urdf/XML/joint)

check the tutorial instalation with

```
$roscd urdf_tutorial
```

check for errors in urdf files, first conver from xacro to urdf

```
$rosrun xacro xacro /path/to/robot.xacro > robot.urdf
$check_urdf robot.urdf
```

1. `$ sudo apt install liburdfdom-tools`

2. `$ rosrun xacro xacro --inorder ${find hrwros_support}/urdf/hrwros.xacro > hrwros.urdf`

3. `$ check_urdf hrwros.urdf `

4. `$ roslaunch hrwros_suport  visualize_hrwros.launch`


### Assignments

Require the singularity environtment available in the course. See [singularity folder](singularity/)

`git clone --depth 1 --branch week4  https://github.com/jcorredorc/ros_edx.git `

1. `$ roslaunch hrwros_week2_assignment visualize_hrwros_assignment1.launch`

2. `$ roslaunch hrwros_week2_assignment visualize_hrwros_assignment2.launch`

3. `$ roslaunch hrwros_week2_assignment visualize_hrwros_assignment3.launch`

 

## Week 3

soon...


## Week 4

### Assignments

Require the singularity environtment available in the course. See [singularity folder](singularity/)


`git clone --depth 1 --branch week4  https://github.com/jcorredorc/ros_edx.git `


1. `$ roslaunch week4_moveit_config setup_assistant.launch`

2. 

```  
    $ roslaunch hrwros_week4_assignment hrwros_week4_environment.launch
    $ roscd hrwros_week4_assignment/scripts
    $ rosrun hrwros_week4 hrwros_moveit_commander_cmdline
    > load week4_assignment2_script
```

3. 

```
    $ roslaunch hrwros_week4_assignment hrwros_week4_environment.launch
    $ roslaunch hrwros_week4_assignment week4_assignment3.launch
```

## Week 5


`git clone --depth 1 --branch week5  https://github.com/jcorredorc/ros_edx.git `


```
$ roslaunch hrwros_gazebo hrwros_environment.launch gui:=false rviz:=true
```

### Assignments


Require the singularity environtment available in the course. See [singularity folder](singularity/)

1. 

```
$ roslaunch hrwros_week5_assignment week5_assignment1.launch
```

```
$ rostopic list
...
/hrwros/new_logical_camera_1
/hrwros/new_logical_camera_2
...
```

```
> rostopic echo /hrwros/new_logical_camera_1 -n1
models: 
  - 
    type: "workcell"
    pose: 
      position: 
        x: 2.000004407832632
        y: -1.8000000000000003
        z: -1.1999926535816976
      orientation: 
        x: -0.7071080798594737
        y: 0.0
        z: 0.0
        w: 0.7071054825112364
pose: 
  position: 
    x: 1.2
    y: 1.8
    z: 2.0
  orientation: 
    x: 0.0
    y: 0.7071080798594737
    z: 0.0
    w: 0.7071054825112364
---
Singularity HRWROS:~>
```

```
> rostopic echo /hrwros/new_logical_camera_2 -n1
models: 
  - 
    type: "robot2_pedestal"
    pose: 
      position: 
        x: 1.7999695123854997
        y: 1.23
        z: 8.300006611713194
      orientation: 
        x: -0.7071080798594737
        y: 0.0
        z: 0.0
        w: 0.7071054825112364
  - 
    type: "workcell"
    pose: 
      position: 
        x: 1.7999695123854997
        y: 1.23
        z: 8.300006611713194
      orientation: 
        x: -0.7071080798594737
        y: 0.0
        z: 0.0
        w: 0.7071054825112364
  - 
    type: "robot2"
    pose: 
      position: 
        x: 1.0999981220770239
        y: -0.2699999319879862
        z: 0.5000040640874971
      orientation: 
        x: -0.5001868618064235
        y: -0.49980823898733373
        z: 0.4997935181189006
        w: 0.5002112221481584
pose: 
  position: 
    x: -8.3
    y: -1.23
    z: 1.8
  orientation: 
    x: 0.0
    y: 0.7071080798594737
    z: 0.0
    w: 0.7071054825112364
---
Singularity HRWROS:~> 
```

2. 

```
roslaunch hrwros_week5_assignment week5_assignment1.launch
```

```
rosrun tf2_tools view_frames.py
```

```
> rosrun tf2_tools echo.py new_logical_camera_2_frame camera_rgb_frame
At time 4488.7, (current time 4488.762)
- Translation: [1.503, 1.006, 4.214]
- Rotation: in Quaternion [-0.177, -0.685, 0.177, 0.685]
            in RPY (radian) [-1.571, -1.065, 1.571]
            in RPY (degree) [-90.000, -61.006, 90.000]
At time 4489.7, (current time 4489.762)
- Translation: [1.503, 1.006, 4.214]
- Rotation: in Quaternion [-0.177, -0.685, 0.177, 0.685]
            in RPY (radian) [-1.571, -1.065, 1.571]
            in RPY (degree) [-90.000, -60.996, 90.000]
At time 4490.7, (current time 4490.762)
- Translation: [1.503, 1.006, 4.214]
- Rotation: in Quaternion [-0.177, -0.685, 0.177, 0.685]
            in RPY (radian) [-1.571, -1.065, 1.571]
            in RPY (degree) [-90.000, -60.995, 90.000]
```

2.1.
```
$ roslaunch hrwros_week5_assignment week5_assignment2_part1.launch
```

2.2.


```
$ rosrun tf2_ros static_transform_publisher 0 0 0.3 0 0 0 1 plate_top_link turtlebot_object_top
```

```
$ roslaunch turtlebot_teleop keyboard_teleop.launch
```
```
$ roslaunch hrwros_week5_assignment week5_assignment2_part2.launch
```

2.3.

```
$ roslaunch hrwros_week5_assignment week5_assignment3.launch
```

```
$ rosservice call /spawn_object_on_turtlebot
```

```
$ rosrun hrwros_week4 hrwros_moveit_commander_cmdline

> use robot2
> go R2PreGrasp
```

```
$ rosrun hrwros_week5_assignment week5_assignment3.py
```



