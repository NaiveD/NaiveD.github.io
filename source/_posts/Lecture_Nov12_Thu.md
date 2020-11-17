---
title: Nov.12 Thu Week10
date: 2020-11-17 13:34:52
tags: Robotics
categories:
    - Courses
    - Fall 2020
    - CS283
    - Lecture Notes
---

# Lec 13 Computer Vision II

## Image Processing

Image filtering
Lena

* lowpass filter
* spatial filters (masks or kernels)

### Spatial filters

Deep Learning
Convolution
pooling

### Linear filters

### Smoothing filters

averaging
矩阵内值的和要为1

* Gaussian Kernel
G = 1/16 [1 2 1; 2 4 2; 1 2 1]
(very popular)
信号处理

Gaussian smoothing preprocessing (popular first step)

平滑 Smoothing e.g. SIST Lobby Scan

## Edge Detection

Edge is where change occurs.

1st derivative max, 2nd derivative 0

### Image gradient

Image: 2-d signal (x and y)

The discrete gradient

* Gradient Edge Detectors
Roberts, Prewitt, Sobel

### Effects of noise

Solution: smooth first

f, h, h * f, 求导(h * f)

* Derivative theorem of convolution
先求导再卷积 = 先卷积再求导

The Canny Edge Detector
Laplacian of Gaussian operator

* thinning: non-maxima suppression 非极大值抑制

## Image Features

* Lines
* Points
  * Harris
  * SIFT

角点

* How to build a Panorama?
  * Detect feature points in both images
  * Find corresponding pairs
  * Use these pairs to align images

### Matching with Features

### Harris Corner Detector

* Finding Corners
  * Key property: image gradient has 2 or more dominant directions
  * Corners are repeatable and distinctive

泰勒展开

SVD分解

* Corner response function

* Harris Properties
