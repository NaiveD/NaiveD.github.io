---
title: ROS Launch
date: 2020-11-17 13:38:49
tags: Robotics
categories:
    - Courses
    - 2020 Fall
    - CS283
    - ROS
---

# ROS Launch
## ROS Launch 文件是什么，如何运行
ROS Launch文件是可以::同时运行多个nodes::的文件。Launch文件以一种特殊的XML格式编写，在ROS packages中使用广泛。

`rosrun`只能运行一个nodes， `roslaunch`可以同时运行多个nodes.

* 运行launch file
`roslaunch package_name launch_file_name`

Launch file可以不在package中，此时需指出该launch文件的绝对路径，即可运行。

`roslaunch absolute_path/launch_file_name`

## 如何创建ROS Launch文件
1. launch文件以`.launch`为后缀，放在ROS package的launch文件夹下。
2. Launch文件是XML文件，每个XML文件必须有一个root element。而launch文件的root element由一对launch 标签定义。
```
<launch>
...
</launch>
```
Launch文件中的其他elements必须都在这一对tags之间。
3. launch文件的核心是一系列node elements，每个node element启动一个node。Node element看起来如下：
```
<node pkg="package_name" type="executable_name" name="node_name"/>
```
如果该node中有其他tag，必须使用以下形式：
```
<node pkg="..." type="..." name = "...">
</node>
```

一个node element必须包含三个属性: `pkg`, `type`, `name`. 
`pkg`和`type`指出ROS应该运行哪个package中的哪个node。
`type`是可执行文件的名称。
`name`是可以任意给出的，它覆盖了原有文件中的`ros::init`制定的`node_name`.

## Including other launch files
include其他launch file中的node和parameters

必须写出该launch文件的全部路径名称，较繁琐。
`<include file=”path-to-launch-file”/>`

常用：
`<include file=”$(find package_name)/launch_file_name”/>`

include也支持ns属性，将它的内容放进指定的namespace。
`<include file=”...” ns=”namespace_name”/>`

## Parameter
The `<param>` tag defines a parameter to be set on the  [Parameter Server](http://wiki.ros.org/Parameter%20Server) . 

Parameters是ROS系统使用的数值，存在parameter server上，nodes可通过`ros::param::get`函数编程得到它，用户可通过`rosparam`获取它。

## Argument
为便于launch文件重构，roslaunch支持launch arguments,也称为arguments或者args，类似于局部变量。

arguments仅在launch文件内部有意义，nodes不能直接获取它们的值。

1. 声明argument
`<arg name="arg_name"/>`

2. 指定argument的值
Launch文件中的每个argument都必须有指定值。赋值方法有好几种。
	* 在命令行赋值   `$ roslaunch package_name launch_file_name arg_name:=arg_value`
	* 在声明argument时赋值:
		* `<arg name=”arg_name” default=”arg_name”/>`
		* `<arg name=”arg_name” value=”arg_name”/>`
		* 上面两行的区别在于，命令行参数可以覆盖default，但是不能重写value的值。
3. 获取argument的值
	* 一旦声明某个argument并赋值后，我们可以通过arg使用该argument.   `$(arg arg_name)`
	* 如果该行出现，roslaunch将会用给定arg_name的值替换其左边的值。
	
4. 将argument值传给included launch文件
```
<include file="path-to-file">
	<arg name="arg_name" value="arg_value"/>
	...
</include>
```

若在launch文件中，launch文件及其包含的launch文件出现相同的arguments，则需在launch文件及included launch文件中同时写：
`<arg name="arg_name" value="$(arg arg_name)"/>`


## Reference
> http://wiki.ros.org/roslaunch  
> [ROS学习之roslaunch | 励志献身SLAM 的 阿翔](http://ttshun.com/2018/05/24/ROS%E5%AD%A6%E4%B9%A0%E4%B9%8Broslaunch/)  
> [ROS launch总结 - Jessica&jie - 博客园](https://www.cnblogs.com/Jessica-jie/p/6961837.html)  