---
title: Sniper
date: 2020-11-17 00:26:07
categories: 
    - Courses
    - Fall 2020
    - TA
    - CS211
    - Lab
tags: Computer Architecture
---

# Learning Sniper

## What is Sniper

**Sniper** is a next-generation parallel, high-speed and accurate **x86 simulator**. It is written in C++.

## How to compile Sniper

### Prerequisites

```shell
OS: Ubuntu 16.04, 18.04, or 20.04
gcc: 7.5.0 or 9.3.0
```

### Steps

1. Get Sniper source code.
2. Input the following commands in the terminal:

**Make sure to use python2**

```shell
$ cd $PATH_TO_SNIPER 
$ sudo dpkg --add-architecture i386
$ sudo apt-get install binutils build-essential curl git libboost-dev libbz2-dev libc6:i386 libncurses5:i386 libsqlite3-dev libstdc++6:i386 python wget zlib1g-dev
$ make
```

## Run a program using Sniper

Sniper is an x86 simulator, it can be used to run executables.

Say you have an executable `program1.exe` and a config file `config1.cfg` under the directory at `$PATH_TO_FILE`. You can run the executable by Sniper with the following commands:

```shell
$ cd $PATH_TO_SNIPER 
$ ./run-sniper -c $PATH_TO_FILE/config1.cfg -- $PATH_TO_FILE/program1.exe
```

## Reference
> [Google Group of Sniper](https://groups.google.com/g/snipersim)