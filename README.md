# ros_edx


## Week1

Read a ultrasound sensor connected to an arduino board (see [here](https://github.com/jcorredorc/udemy_ros_beginners#arduino)). 


```
roslaunch udemy_ros_beginners arduino_hcsr04.launch
```

Then publish the data in the custom message `SensorInformation.msg`

This script `sensor_info_publisher.py` is modified from the course objective, it reads the real sensor and publishes the data in the message `SensorInformation.msg`


```
rosrun ros_edx sensor_info_publisher.py
```

### Assignments

1a. this script subscribe to `/sensor_info` and check if the data is less than 0.1.

```
rosrun ros_edx week1_assignment1_part1.py 
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

check the folder instalation with

```
roscd urdf_tutorial
```

check for errors in urdf files, first conver from xacro to urdf

```
rosrun xacro xacro /path/to/robot.xacro > robot.urdf
check_urdf robot.urdf
```

1. `sudo apt install liburdfdom-tools`

2. `rosrun xacro xacro --inorder ${find hrwros_support}/urdf/hrwros.xacro > hrwros.urdf`

3. `check_urdf hrwros.urdf `

4. `roslaunch hrwros_suport  visualize_hrwros.launch`


### Assignments

Require the singularity environtment available in the course. See [singularity folder](singularity/)

`git clone --depth 1 --branch week4  https://github.com/jcorredorc/ros_edx.git `

1. `roslaunch hrwros_week2_assignment visualize_hrwros_assignment1.launch`

2. `roslaunch hrwros_week2_assignment visualize_hrwros_assignment2.launch`

3. `roslaunch hrwros_week2_assignment visualize_hrwros_assignment3.launch`

 

## Week 3

soon...


## Week 4

### Assignments

Require the singularity environtment available in the course. See [singularity folder](singularity/)


`git clone --depth 1 --branch week4  https://github.com/jcorredorc/ros_edx.git `


1. `roslaunch week4_moveit_config setup_assistant.launch`

2. 

```  
    roslaunch hrwros_week4_assignment hrwros_week4_environment.launch
    roscd hrwros_week4_assignment/scripts
    rosrun hrwros_week4 hrwros_moveit_commander_cmdline
    > load week4_assignment2_script
```

3. 
    `roslaunch hrwros_week4_assignment hrwros_week4_environment.launch`

    `roslaunch hrwros_week4_assignment week4_assignment3.launch`


## Week 5






