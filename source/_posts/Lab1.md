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


## Cache Inclusion Policy

* Inclusive: 高层级cache中的数据全部出现在低层级cache中
  * cache层级：数字越小，层级越高 (e.g. L1高，L2低)
  * Lower level cache is inclusive of the higher level cache (e.g. L2 is inclusive of L1)

* Exclusive: 低层级cache只含有不在高层级cache中出现的数据
  * Lower level cache is exclusive of the higher level cache (e.g. L2 is exclusive of L1)

* Non-Inclusive Non-Exclusive (NINE): 低层级cache既不是严格incluseive，也不是严格exclusive of the 高层级cache