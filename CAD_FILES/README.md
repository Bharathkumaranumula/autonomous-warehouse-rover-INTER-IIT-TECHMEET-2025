
# ETERNAL Robotic Lifting System - CAD Files Folder

**Project:** ETERNAL Mechanism  
**Type:** Robotic Lifting & Mobility System  
**File Format:** STEP (.step)

---

##  Overview

The **ETERNAL mechanism** is a robotic lifting and mobility system designed around a scissor mechanism mounted onto a mobile chassis. The system integrates vertical motion through a Z-axis actuator, real-time sensing through an Intel RealSense D455i camera, and wheel-based locomotion.

This repository contains the STEP files required to view, analyze, or manufacture the mechanical assembly.

---

##  File Structure & Component Manifest

Below is a detailed breakdown of the subsystems and their corresponding CAD files.

### 1. Main Assembly Structure
**File:** `MAIN_BODY.step`
* **Purpose:** The primary chassis and structural base for the complete mechanism.
* **Mounting Position:** Acts as the base foundation. All major components—including the scissor mechanism, drive motors, slider guides, and electronics—interface directly with this part.

### 2. Scissor Mechanism
**Files:** `FIXED_SCISSOR_MOUNTING_BOTTOM.step`
* **Purpose:** Lower mounting base for the scissor mechanism.
* **Mounting Position:** Rigidly attached to the main chassis; holds the bottom hinge points.

**Files:** `SCISSOR_MECHANISM_LINK-1.step` / `SCISSOR_MECHANISM_LINK-2.step`
* **Purpose:** The primary link arms forming the cross-bar structure of the scissor lift.
* **Mounting Position:** Assembled with pivot joints to form the extendable mechanical linkage.

**File:** `SCISSOR_MECHANISM_SLIDER_SLOT.step`
* **Purpose:** Linear guide slot used to guide the motion of the scissor pivot.
* **Mounting Position:** Attached to the chassis or slider platform.

### 3. Slider and Support System
**Files:** `SLIDER_MOUNT_TYPE_1.step` / `SLIDER_MOUNT_TYPE_2.step`
* **Purpose:** Slider support assemblies ensuring smooth linear travel.
* **Mounting Position:** Located along the slider slot and support rails.

### 4. Actuation and Mobility
**File:** `Z_AXIS_ACTUATIOR_MOTOR_MOUNT.step`
* **Purpose:** Motor bracket for the Z-axis actuator (leadscrew or linear actuator).
* **Mounting Position:** Connected to the chassis, aligned with the lift’s thrust axis.

**File:** `WHEEL_MOTOR_SUPPORT_MOUNT.step`
* **Purpose:** Housing mount for the drive motors controlling robot locomotion.
* **Mounting Position:** Located on the lower-side faces of the chassis.

### 5. Sensing and Vision
**File:** `CAMERA_MOUNT.step`
* **Purpose:** Dedicated mount for the **Intel RealSense D455i** depth camera.
* **Mounting Position:** Placed behind the main actuator or rear side of the motor assembly, facing forward. Used for SLAM, mapping, and perception.

---

##  System Summary

| Subsystem | Components | Functional Purpose |
| :--- | :--- | :--- |
| **Chassis** | `MAIN_BODY` | Structural base and interface for all modules |
| **Lifting System** | Links + Slider components | Vertical movement (Scissor Lift) |
| **Actuator** | Z-axis motor mount | Power transmission for lift |
| **Drive** | Wheel motor support mounts | Horizontal mobility |
| **Vision** | Camera mount | Environment perception & navigation |

---

##  Usage
These files are provided in **.STEP** format, which is widely supported by standard CAD software including:
* SolidWorks
* Autodesk Fusion 360
* FreeCAD
* Onshape

To view the full assembly, import `MAIN_BODY.step` first, followed by the sub-components using the mounting positions described above.

---
*Documentation generated for the ETERNAL CAD Project.*
