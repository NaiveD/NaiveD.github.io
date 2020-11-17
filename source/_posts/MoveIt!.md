---
title: MoveIt!
date: 2020-11-17 13:48:33
tags: Robotics
categories:
    - Courses
    - 2020 Fall
    - CS283
    - ROS
---

# MoveIt!
## Move Group (ROS Node) C++ Interface
In MoveIt, the simplest user interface is through the `MoveGroupInterface` class.

提供了简单的方式来 setting joint or pose goals, creating motion plans, moving the robot, adding objects into the environment and attaching/detaching objects from the robot. 

This interface communicates over ROS topics, services, and actions to the MoveGroup Node.
