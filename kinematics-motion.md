---
layout: blog
title: Kinematics-motion
permalink: /kinematics-motion/
---

<style>
  body {
    margin: 0 auto;
    max-width: 1100px;
    /* padding: 10px; */
    font-family: Arial, sans-serif;
    font-size: 16px; /* Increase font size */
    line-height: 1.6;
  }
  h1 {
    font-size: 40px; /* Increase size of h2 */
    margin-bottom: 15px;
  }
  h2 {
    font-size: 25px; /* Increase size of h2 */
    margin-bottom: 15px;
  }
</style>

<div class="row">
    <div class="col-lg-12 text-center">
        <div class="navy-line"></div>
        <h1><strong>Robot Kinematics and Motion Planning</strong></h1>
    </div>
</div>

<br>

## A<sup>*</sup> Search Algorithm
I implemented a heap data structure (priority queue) and A<sup>*</sup> Search Algorithm, using Euclidean distance to the goal as an admissible heuristic.

<img src="/astar.gif" alt="AStar" width="450" height="450">

<br>

## Physical Simulation of a Simple Pendulum

I implemented the physical dynamics and servo controller for a simple 1 degree-of-freedom robot system. This system is 1 DOF robot arm as a frictionless simple pendulum with a rigid massless rod and idealized motor.

<img src="/pendularm.gif" alt="AStar" width="450" height="450">

<br>

## Forward Kinematics

I rendered the forward kinematics of an arbitrary robot, given an arbitrary kinematic specification by computing matrix coordinate frame transforms for each link and joint of the robot based on the parameters of its hierarchy of joint configurations. I also implemented Axis-Aligned Bounding Box (AABB) collision detection, using AABB/Sphere tests. The red wireframe that is highlighted on the robot shows the part of the robot that is colliding with a part of the environment or obstacle (collision detection).

<img src="/forwardkinematics.gif" alt="AStar" width="450" height="450">

<br>

## Inverse Kinematics

I implemented inverse kinematics through gradient descent optimization with both the Jacobian Transpose and Jacobian Pseudoinverse methods, so that the robot to reaches a given point in space for position control of the robot endeffector.

<img src="/inversekinematics.gif" alt="AStar" width="450" height="450">

<br>

## Motion Planning

I implemented the RRT-Connect Search Algorithm to be used for a collision-free motion planner to enable the robot to navigate from a random configuration in the world to its home configuration (or "zero configuration"). The motion planner renders yellow "breadcrumb" indicators of base positions explored, and once a viable motion plan is found, the path is highlighted by turning red.

<div style="text-align: center;">
    <img src="/rrtconnect.gif" alt="AStar" width="450" height="450" style="margin-right: 5%;">
    <img src="/rrtmotion.gif" alt="AStar" width="500" height="450">
</div>