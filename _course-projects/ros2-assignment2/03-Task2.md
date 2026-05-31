---
layout: default
title: Task2
permalink: /course-projects/ros2-assignment2/task2/
---

## 1. Modified World (5 Marks)
Full Marks Requirements:
World2 recreated
Internal walls added
Navigation space preserved
## 2. Navigation to Point C (5 Marks)
Full Marks Requirements:
Robot reaches Point C
Uses laser scan data
## 3. Navigation to Point D (5 Marks)
Full Marks Requirements:
Robot dynamically avoids obstacles
Behaviour adapts to environment
## 4. Final Navigation to Point B (5 Marks)
Full Marks Requirements:
Robot completes A → C → D → B
Continuous decision-making
No hard-coded path
## 5. Keynotes & how it works

```mermaid
flowchart TD
    START([Start Task 2]) --> LAUNCH[Launch Gazebo world with obstacles]
    LAUNCH --> SPAWN[Spawn robot]
    SPAWN --> NODE[Start navigation node]
    
    NODE --> ODOM[Read position from /odom]
    ODOM --> SCAN[Read laser data from /scan]
    
    SCAN --> CHECK_OBS{Obstacle detected?}
    
    CHECK_OBS -->|No| MOVE_TARGET[Move towards target]
    CHECK_OBS -->|Yes| STOP[Stop forward motion]
    
    STOP --> TURN[Rotate to find clear path]
    TURN --> SCAN
    
    MOVE_TARGET --> CMD[Publish /cmd_vel]
    CMD --> CHECK_GOAL{Target reached?}
    
    CHECK_GOAL -->|No| ODOM
    CHECK_GOAL -->|Yes| END([Stop robot])

```
