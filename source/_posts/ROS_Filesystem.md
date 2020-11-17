---
title: ROS Filesystem
date: 2020-11-17 13:38:49
tags: Robotics
categories:
    - Courses
    - Fall 2020
    - CS283
    - ROS
---

# ROS Filesystem
* **Packages**: the software organization unit of ROS code, can contain libraries, executables, scripts, or other artifacts.
* **Manifests** (package.xml): a description of a *package*, defines dependencies between packages, captures meta information about the *package* like version, maintainer, license, etc...

## Filesystem Tools
`rospack`, `roscd`, and `rosls`
```
$ rospack find [package_name]	# returns the package path
$ roscd [locationname[/subdir]] 
$ rosls [locationname[/subdir]]
```
