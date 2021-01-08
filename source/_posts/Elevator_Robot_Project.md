---
title: Elevator Robot Project
date: 2020-11-17 13:38:49
tags: Robotics
categories:
    - Courses
    - Fall 2020
    - CS283
    - Project
---

# Elevator Robot Project

A project of the 2020 Robotics Course of the School of Information Science and Technology (SIST) of ShanghaiTech University
<https://robotics.shanghaitech.edu.cn/teaching/robotics2020>

Team Member: Zhai Keyan, Li Chu'an, Zhang Ge
Supervisor: Hou Jiawei, Sören Schwertfeger

## Introduction

In this project, we tried to make a robot capable of taking elevators autonomously. With the ability to take elevators and move vertically inside a building, the mobility of wheeled robots can be significantly improved.

## System Description

### Hardware

Our elevator robot includes a complex hardware system consists of the following parts:

* **Base platform** - Jackal
* **Manipulator** - Kinova
* **Camera** - Intel Realsense
* **3D LiDAR** - Velodyne

![The Elevator Robot](Elevator_Robot.JPG)

### Software

The whole software system is a multi-phased pipeline based on ROS melodic on Ubuntu 18.04.

* **Localization and Navigation** - AMCL algorithm

![AMCL Navigation](Navi.png)

* **Button Detection** - OCR-RCNN algorithm

![Button Detection](Button_Detect.JPG)

* **Button Push** - MoveIt!

![Button Push](Button_Push.jpg)

The upper left image indicates a random starting pose of the manipulator, represented by the orange arm in RViz in the right.

The lower left image indicates the target pose of the manipulator where it pushes the button with the pose represented by the red arrow in RViz in the right.

## Demos

<!-- Add Video -->
Video to be added.
