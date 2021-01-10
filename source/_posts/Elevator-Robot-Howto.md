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
* Set target pose with `2D Nav goal`

## Button Detection

* Starting the button detection
  
  * On server (requires 2GB GPU):
    * Pre-requisties: `Tensorflow`, `flask`
    * Clone [OCR-RCNN: An Accurate and Efficient Framework for Elevator Button Recognition](https://github.com/Dzhange/ocr-rcnn-v2) to server
    * Download pre-trained weights as described in the repo above.
    * run `python server_inference.py`, this will start a flask server on port `30001`.
    <!-- * Copy the code in `folder` (stored on the robot) to the server -->
    
    <!-- * Run `python detect_ros.py` on the robot./ -->

  * On robot, run the following commands:
    Configure IP address of the server on robot to communicate with the robot
    ```shell
    $ cd elevator_ws/src/elev_button_detection/src/
    $ python detect_ros.py
    ```

## Button push

* Start button push
    `roslaunch elev_button_push elev_button_push.launch`
