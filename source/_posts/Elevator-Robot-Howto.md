---
title: Elevator Robot How to
date: 2021-01-07 22:42:26
tags: Robotics
categories:
    - Courses
    - Fall 2020
    - CS283
    - Project
---

# Elevator Robot How to

Start Jackal for ROS:

Prepare robot, including camera, velodyne, kinova, tf:
`$ roslaunch prepare_kinova_realsense prepare_kinova_realsense.launch`

For visualization:
`$ rosrun rviz rviz`
Use config at `~/.rviz/elevator.rviz`

## PS3 Controller
joystick control: `sudo sixad -s`

[PS3 controller usage](https://support.playstation.com/s/article/PS3-Pair-and-Assign-Controllers?language=en_US)


## Run Navigation
Run `$ roslaunch mb_setting amcl_demo.launch`

* Set `Fixed Frame` in `Global Options` as `map`
* Set initial pose with `2D Pose Estimate`

## Button Detection
[MARS_button_detection Readme](https://star-center.shanghaitech.edu.cn/gitlab/MARS/MARS-Manipulation/mars_button_detection/-/blob/master/README.md)

[OCR-RCNN: An Accurate and Efficient Framework for Elevator Button Recognition](https://github.com/zhudelong/ocr-rcnn-v2)

* Data for testing
    Recorded bag of button images in `~/elevator_project/button.bag`

* Starting the button detection

    launch detection node: 
    `roslaunch elev_button_detection detect.launch`

* Start button push
    `roslaunch elev_button_push elev_button_push.launch`
