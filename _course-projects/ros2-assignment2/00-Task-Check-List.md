---
layout: default
title: Task Check List
permalink: /course-projects/ros2-assignment2/task-check-list/
---

## Task 1 — 15 Marks
- [ ] World1 recreated in Gazebo (walls scaled and enclosed)
- [ ] Robot created and placed at Point A
- [ ] Laser scanner mounted on robot
- [ ] Screenshot of Gazebo world (evidence)
- [ ] Screenshot of robot in world (evidence)

### Integration of Gazebo with ROS
- [ ] Robot spawns using ROS 2 launch file
- [ ] `/cmd_vel` topic controls robot movement
- [ ] `/scan` topic publishes laser data
- [ ] No runtime errors when launching
- [ ] Verify with `ros2 topic list`
- [ ] Verify with `ros2 topic echo /scan`
- [ ] Demonstrate robot moving via ROS command

### Navigation A → B
- [ ] Robot reaches Point B
- [ ] Movement is controlled and logical
- [ ] Code is readable and well structured
- [ ] (Optional) Timed movement or simple directional control implemented

## Task 2 — 20 Marks
- [ ] World2 recreated with internal walls
- [ ] Navigation space preserved after modifications

### Navigation to Point C
- [ ] Robot reaches Point C
- [ ] Solution uses laser scan data (`/scan`)

### Navigation to Point D
- [ ] Robot dynamically avoids obstacles
- [ ] Behaviour adapts to changing environment

### Final Navigation A → C → D → B
- [ ] Robot completes sequence A → C → D → B
- [ ] Continuous decision-making (no hard-coded path)

## Task 3 — 30 Marks
- [ ] World3 recreated with obstacles (box, sphere, cylinder)
- [ ] Obstacles spaced and distributed appropriately

### Navigation to Point C
- [ ] Robot avoids obstacles reliably (no collisions or minimal corrections)

### Navigation to Point D
- [ ] Robot handles tighter spaces without failure
- [ ] Behaviour remains stable in constrained areas

### Final Navigation A → C → D → B
- [ ] Smooth, continuous movement between points
- [ ] Minimal stopping or jerking
- [ ] Uses real-time scan data for decisions
