---
title: ROS Workspace
date: 2020-11-17 13:38:49
tags: Robotics
categories:
    - Courses
    - Fall 2020
    - CS283
    - ROS
---

# ROS Workspace
## Create a ROS workspace
::Create and build a **catkin workspace**:::
```
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/
$ catkin_make
```

This will create a `CMakeLists.txt` link in your `src/` folder.
This will also create a `build/` and `devel/` folder in your current working directory.
Inside `devel`, there are several `setup.*sh` files. Source any of them to overlay this workspace on top os your environment.

`$ source devel/setup.*sh`

Make sure `ROS_PACKAGE_PATH` environment variable includes the directory.
```
$ echo $ROS_PACKAGE_PATH
/home/zhaiky/cakin_ws/src:/opt/ros/melodic/share
```


## **catkin workspaces**: 
**catkin workspaces** can be built as 
1. A standalone project, like normal `cmake` projects
2. Also provides the concept of workspaces, where you can build multiple, interdependent packages together all at once.

A **catkin workspace** is a **folder** where you modify, build, and install **catkin packages**. 

Typical **catkin workspace** layout:
```
workspace_folder/         -- WORKSPACE
  src/                    -- SOURCE SPACE
    CMakeLists.txt        -- The 'toplevel' CMake file
    package_1/
      CMakeLists.txt
      package.xml
      ...
    package_n/
      CATKIN_IGNORE       -- Optional empty file to exclude 									package_n from being processed
      CMakeLists.txt
      package.xml
      ...
  build/                  -- BUILD SPACE
    CATKIN_IGNORE         -- Keeps catkin from walking this 									directory
  devel/                  -- DEVELOPMENT SPACE (set by 											CATKIN_DEVEL_PREFIX)
    bin/
    etc/
    include/
    lib/
    share/
    .catkin
    env.bash
    setup.bash
    setup.sh
    ...
  install/                -- INSTALL SPACE (set by 		 										CMAKE_INSTALL_PREFIX)
    bin/
    etc/
    include/
    lib/
    share/
    .catkin             
    env.bash
    setup.bash
    setup.sh
    ...
```

Four spaces: `src/`, `build/`, `devel/`, and `install/`.

### Source Space `src/` 
* contains source code of catkin packages
* where you can extract/checkout/clone source code for the packages you want to build.
* each folder `package_1`...`package_n` within the source space contains one or more **catkin packages**

### Build Space `build/`
* where `CMake` is invoked to build the catkin packages in the source space

### Development Space `devel/`
* where built targets are placed prior to being installed

### Install Space `install/`
* Once targets are built, they can be installed into the install space by invoking the install target.

