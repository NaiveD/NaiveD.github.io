---
title: Lab1
date: 2020-11-18 01:27:18
tags: Computer Architecture
categories:
    - Courses
    - Fall 2020
    - TA
    - CS211
    - Lab
---

# Lab 1 

## Optimal Replacement Policy

Optimal replacement is to evict a cache block with the longest reuse distance in the future. 
To implement optimal replacement policy, we need to know the memory access trace in the future.

This is impossible in real CPUs, but in a simulator like Sniper, we can model it.

We need to do one or multiple passes of memory references of both instructions and data for a program. Sniper can produce a trace of memory references, with which we can develop our optimal replacement by looking ahead of the future. To facilitate the implementation, we can consider doing an offline analysis of the trace to help our afterward online replacement, or do them simultaneously in one online round, or both.

### How to get Memory Access Trace

Refer to: 
1. [How to print out the trace containing only the memory-accessing instructions of a multi-threaded benchmark in a per-thread manner?](https://groups.google.com/g/snipersim/c/WMNVKJvw3PU/m/55UjDEubAGQJ?pli=1)
2. [Obtaining application's memory trace](https://groups.google.com/g/snipersim/c/4CnjYwSagT4/m/Dc5FPYr3ZnYJ?pli=1)

