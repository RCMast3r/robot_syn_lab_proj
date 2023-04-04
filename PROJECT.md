1. [joint position control](https://github.com/Kinovarobotics/kinova-ros#joint-position-control):
    
    pre-reqs:

    - launch the driver with rviz vizualualization:

    ```roslaunch kinova_bringup kinova_robot.launch kinova_robotType:=j2n6s300 use_urdf:=true```

    be sure to source the workspace to be able to load the urdf and then launch rviz and visualize the robot model in rviz

    ```rosrun rviz rviz```

    home the boi:
    
    ```rosservice call j2n6s300_driver/in/home_arm```

    control the arm by adding +10 degrees to the first joint:

    ```rosrun kinova_demo joints_action_client.py -v -r j2n6s300 degree -- 10 0 0 0 0 0```

2. [cartesian position control](https://github.com/Kinovarobotics/kinova-ros#cartesian-position-control)
    
    ```rosrun kinova_demo pose_action_client.py -v -r j2n6s300 mdeg -- 0.01 0 0 0 0 10```

3. [finger position control](https://github.com/Kinovarobotics/kinova-ros#finger-position-control)
    
    ```rosrun kinova_demo fingers_action_client.py j2n6s300 percent -- 100 100 100```


4. gazebo

    ```roslaunch kinova_gazebo robot_launch.launch kinova_robotType:=j2n6s300```


    home robot in gazebo:
        ```rosrun kinova_control move_robot.py j2n6s300```

    moveit with gazebo robot arm control:

    ```roslaunch j2n6s300_moveit_config j2n6s300_gazebo_demo.launch```

5. kinova arm moveit
    
    ```roslaunch kinova_bringup kinova_robot.launch kinova_robotType:=j2n6s300```

    ```roslaunch j2n6s300_moveit_config j2n6s300_demo.launch```