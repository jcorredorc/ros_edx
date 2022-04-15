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
    $rosrun ros_edx week1_assignment1_part1.py 
    ```
1b. Creates a custom message

    ```
    $ rosmsg show ros_edx/BoxHeightInformation 
    float64 box_height
    ```

1c. create a node with a puclisher and subscriber
    ```
    $ rosrun ros_edx sensor_info_publisher.py
    $ rosrun ros_edx week1_assignment1_part1.py
    $ rosrun ros_edx week1_assignment1_part3.py
    ```