---
title: ROS Package
date: 2020-11-17 13:38:49
tags: Robotics
categories:
    - Courses
    - Fall 2020
    - CS283
    - ROS
---

# ROS Package
### Creating a ROS Package
Requirements for a catkin package:
* Must contain `package.xml`, which provides meta information about the package
* Must contain `CMakeLists.txt`, which uses **catkin**.
* Each package must have its own folder

Simplest package structure:
```
my_package/
	CMakeLists.txt
	package.xml
```

### Packages in a catkin Workspace
* Using a catkin workspace to work with catkin packages is recommended. Refer to {% post_link ROS_Workspace %}

* You can also build catkin packages standalone.

### Creating a catkin Package
 
