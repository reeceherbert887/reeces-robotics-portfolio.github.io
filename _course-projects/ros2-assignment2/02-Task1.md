---
layout: default
title: Robotics Assignment 2
permalink: /course-projects/ros2-assignment2/task1/
---

## 1. World + Robot Setup (2 Marks)
Full Marks Requirements:
World1 correctly recreated in Gazebo
Walls properly scaled and enclosed
Robot created and placed at Point A
Laser scanner mounted visibly on top
Evidence:
Screenshot of Gazebo world
Screenshot of robot in world
## 2. Integration of Gazebo with ROS (5 Marks)
Full Marks Requirements:
Robot spawns using ROS 2 launch file
/cmd_vel topic controls movement
/scan topic publishes data
No runtime errors
Evidence:
ros2 topic list
ros2 topic echo /scan
Robot moving via ROS command

HIGH VALUE SECTION – MUST WORK CLEANLY

## 3. Navigation A → B (8 Marks)
Full Marks Requirements:
Robot reaches Point B
Movement is controlled and logical
Code is readable and structured
Acceptable:
Timed movement
Simple directional control
NOT required:
Collision avoidance
## 4. Keynotes & how it works

```mermaid
flowchart TD
    A[Start Task 1] --> B[Create basic Gazebo world]
    B --> C[Design differential drive robot model]
    C --> D[Add chassis, two wheels and rear castor]
    D --> E[Add laser scanner to robot]
    E --> F[Add Gazebo ROS plugins]
    F --> G[Diff drive plugin publishes /odom and subscribes to /cmd_vel]
    G --> H[Laser plugin publishes /scan]
    H --> I[Create launch file]
    I --> J[Launch Gazebo world]
    J --> K[Spawn robot using /spawn_entity]
    K --> L[Run navigation node go_to_b.py]
    L --> M[Read robot position from /odom]
    M --> N[Calculate distance and angle to target]
    N --> O[Publish velocity command to /cmd_vel]
    O --> P{Target reached?}
    P -- No --> M
    P -- Yes --> Q[Stop robot]
    Q --> R[Task 1 complete]

```
