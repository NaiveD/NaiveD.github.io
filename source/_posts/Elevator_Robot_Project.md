---
title: Elevator Robot Project
date: 2020-11-17 13:38:49
tags: Robotics
categories:
    - Courses
    - 2020 Fall
    - CS283
    - Project
---

# Elevator Robot Project
每次开机

Start Jackal for ROS:
`$ roslaunch jackal_base base.launch` 开机已经自动启动了

目录位置：
`~/catkin_ws/src/jackal_robot/`

Prepare robot, including camera, velodyne, kinova, tf:
`$ roslaunch prepare_kinova_realsense prepare_kinova_realsense.launch`

For visualization:
`$ rosrun rviz rviz`
Use config at `~/.rviz/elevator.rviz`

## PS3 Controller
joystick control: `sudo sixad -s`

[PS3 controller usage](https://support.playstation.com/s/article/PS3-Pair-and-Assign-Controllers?language=en_US)

并不能用，之后有时间再修。


## Run Navigation
Run `$ roslaunch mb_setting amcl_demo.launch`

* Global Options里设置Fixed Frame为map
* 然后2D Pose Estimate箭头手动设置初始位置


## Button Detection
[MARS_button_detection Readme](https://star-center.shanghaitech.edu.cn/gitlab/MARS/MARS-Manipulation/mars_button_detection/-/blob/master/README.md)

* Data for testing
Recorded bag of button images in `~/elevator_project/button.bag`

* Starting the button detection

launch detection node: 
`roslaunch mars_button_detection detect.launch`

* Start button push
`roslaunch mars_button_push mars_button_push.launch`
