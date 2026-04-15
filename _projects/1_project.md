---
layout: page
title: Control and Velocity Kinematics – 4DoF OpenManipulator-X Robotic Arm
description: Cartesian Velocity Control, Jacobian-Based IK, and PD Control
img: assets/img/openm_pick_place_fast.gif
importance: 7
category: work
redirect: https://github.com/NishanthAdithya?tab=repositories
---

## 🎥 Demo Video

<video width="100%" controls loop muted playsinline class="rounded z-depth-1">
  <source src="{{ '/assets/video/Team_4_RBE500_openm_pick_n_place.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>

<div class="caption">
Pick-and-place demonstration using Cartesian velocity kinematics on a 4-DoF OpenManipulator-X.
</div>

---

## 📌 Project Overview

This project implements **velocity-level kinematics control** for a 4-DoF OpenManipulator-X robotic arm.  
The controller maps Cartesian end-effector velocities to joint velocities using the **Jacobian pseudo-inverse**, enabling smooth pick-and-place motion in task space.

---

## 🧠 Key Components
- Forward & Differential Kinematics
- Jacobian derivation (analytic)
- Velocity IK with singularity handling
- ROS 2 control pipeline
- Real-time execution on OpenManipulator-X

---

## 📷 System & Results

<div class="row">
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/openm_kinematics.png"
       title="Kinematic Model"
       class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm mt-3">
    {% include figure.liquid path="assets/img/openm_pick_place.png"
       title="Pick and Place Task"
       class="img-fluid rounded z-depth-1" %}
  </div>
</div>

<div class="caption">
Left: Kinematic model and coordinate frames.  
Right: Pick-and-place task execution.
</div>

---

## ⚙️ Technologies
- **ROS 2 (Humble)**
- **Python / C++**
- **Jacobian-based Velocity IK**
- **OpenManipulator-X**

---

## 📎 Notes
- The controller supports **Cartesian x, y, z velocity commands**
- Singularities handled via damped least squares
- Designed for real-time execution on hardware
