---
title: Nov.10 Tue Week10
date: 2020-11-17 13:38:49
tags: Robotics
categories:
    - Courses
    - Fall 2020
    - CS283
    - Lecture Notes
---

# Lec12 Computer Vision I

## Computer Vision

* Pinhole camera 小孔成像

* Shrinking the aperture 对焦

solution: adding a lens 凸透镜
所有光线都可通过，光强增强

Thin lens equation: 1/d0 + 1/di = 1/f
f, di 已知，可估计d0

Pin-hole Model

## Radial distortion
* Barrel distortion
* Pincushion distortion

## Camera Calibration
刚体变换

How many parameters do we need to model a camera?
11

intrinsic + extrinsic
内参 + 外参

calibration board 标定板

## Stereo Vision
* How do we measaure distancces with cameras?
2 cameras

* Structure from motion

Disparity 

* Correspondence Problem

Epipolar Rectification

* 3D Reconstruction via triangulation
refinement

* Stereo Camera Calibration
齐次坐标

distortion 畸变 

Realsense

* Structure from motion
5点法

* Multiple-view structure from motion

* Optical Flow 光流法

* Color Tracking
