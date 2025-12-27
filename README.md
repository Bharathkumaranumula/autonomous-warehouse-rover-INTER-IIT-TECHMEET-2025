# Autonomous Rover for Warehouse Rack Inventory Management

## About the Project
This project was developed as part of **Inter IIT Tech Meet 14.0** under the problem statement **“Autonomous Rover for Warehouse Rack Inventory Management.”**  
The objective was to design and build an autonomous wheeled robot capable of navigating warehouse aisles and performing **reliable vertical inventory scanning up to 2 meters**.

The system aims to replace slow, unsafe, and error-prone manual inventory audits with a compact, accurate, and scalable robotic solution suitable for modern warehouse environments.

---

## My Contribution
I was responsible for the **entire hardware design and implementation** of this project. My role covered the complete hardware lifecycle, including mechanical design, structural layout, drive system selection, Z-axis scissor lift design, power system architecture, safety mechanisms, and hardware integration.

I led the hardware development from problem understanding and calculations through CAD design, fabrication, assembly, and testing, ensuring the system met competition constraints and performed reliably during integrated operation.

---

## Problem Statement Summary
Modern warehouses face several challenges:
- Manual inventory audits take **10–15 minutes per rack**
- Human errors lead to **30–50% stock mismatches**
- Ladder-based high-rack inspections are unsafe
- Inventory data lacks real-time visibility

The robot must:
- Navigate narrow warehouse aisles autonomously
- Detect and align with storage racks
- Perform vertical scanning across multiple shelf levels (up to ~2 m)
- Reliably capture QR-based inventory data
- Operate safely within strict size and weight constraints

---

## Proposed Solution
The solution is a **compact autonomous differential-drive rover** equipped with a **centrally mounted multi-stage scissor lift** for vertical scanning.

Key system capabilities include:
- Autonomous indoor navigation
- Vertical scanning up to ~1.8–2.0 m
- High QR scanning accuracy
- Modular mechanical and electrical design
- Robust safety and fail-safe mechanisms

---

## System Overview
- Robot type: Autonomous wheeled mobile robot  
- Drive type: Differential drive (2 powered wheels + 2 ball casters)  
- Vertical actuation: Four-stage scissor lift  
- Maximum scanning height: ~1.8–2.0 m  
- Total system mass: ~20 kg  
- Footprint: 570 × 355 mm  
- Compute: NVIDIA Jetson AGX Xavier  
- Low-level control: ESP32  

---

## Hardware Architecture

### 1. Chassis and Structural Design
- Dimensions: **570 × 355 × 145 mm**
- Ground clearance: **25 mm**
- Total mass: **≈ 20 kg**
- Material: **6062 aluminium T-slot profiles (20 × 20 mm)**
- Closed-box frame topology for improved stiffness
- Low and centrally placed mass for anti-tip stability
- Modular mounting surfaces for rapid iteration

---

### 2. Locomotion System (X–Y Motion)
- Drive configuration: **2-wheel differential drive**
- Support: Front and rear metal ball casters
- Turning radius: **0 mm (on-the-spot rotation)**
- Drive wheel diameter: **100 mm**
- Wheel width: **25 mm**
- Motors: **RMCS 2012 DC motors**
  - Voltage: 18 V  
  - Gearbox: 1:25 planetary  
  - Rated torque: 39 kg·cm  
  - Encoders: ~1300 CPR at wheel  
- Direct-drive layout for minimal backlash
- Stability and torque validated with conservative acceleration limits

---

### 3. Z-Axis Scissor Lift Mechanism
- Mechanism: **Four-stage scissor lift**
- Actuation: Horizontally oriented lead screw
- Camera height range: **~320 mm to ~1780 mm**
- Usable vertical coverage: **~1800 mm**
- Shelf levels supported: **5 discrete heights**
- Vertical accuracy target: **±20 mm**
- Achieved repeatability: **~9–18 mm**
- Anti-sway achieved through symmetric geometry and tight-fit bearings
- Mechanical hard stops and limit switches for safety

---

### 4. Power System
- Three independent Li-Po batteries:
  - Jetson AGX Xavier
  - Drive motors
  - Z-axis motor
- 25C discharge capability
- Power Management Unit (PMU) for regulated distribution
- Electrical isolation between compute and motors
- Live battery monitoring and diagnostics

---

### 5. Control Electronics
- Microcontroller: **ESP32 DevKit-V1**
- Motor drivers: **Cytron MDD20A**
- Encoder-based closed-loop PID control
- UART communication between ESP32 and Jetson
- PCB designed with separate logic and power zones for reliability

---

### 6. Safety Systems
- Electronic kill switch (power cut-off)
- Physical emergency stop (E-stop)
- Z-axis limit switches and bump switch
- Firmware-level command clamping
- Software-triggered emergency stop on fault detection

---

## Hardware–Software Integration
- ESP32 handles real-time motor control and encoder feedback
- Jetson AGX Xavier handles perception, mapping, and planning
- ROS2 hardware interfaces synchronize:
  - X–Y motion
  - Z-axis positioning
  - Scanning tasks
- Closed-loop feedback ensures stable and repeatable operation

---

## Testing and Validation
Hardware validation included:
- Static load and structural stability tests
- Drive torque and acceleration verification
- Full-stroke Z-axis endurance testing
- Vertical positioning repeatability tests
- Integrated navigation + lift + scanning runs

### Key Results
- Vertical repeatability: **≤ 18 mm**
- Platform tilt at maximum lift: **≤ 1.3°**
- QR scanning success rate: **96% first pass, 100% with rescan**
- No jamming or over-current events observed

---

## Key Hardware Highlights
- Horizontally actuated scissor lift within base footprint
- Modular T-slot chassis acting as a mechanical backplane
- Differential drive optimized for stability and control simplicity
- COTS-heavy, serviceable, and student-replicable design
- Hardware decisions driven by safety and testability

---

## Documentation
Detailed mechanical design, calculations, CAD models, testing procedures, and validation results are available in the **attached technical report** provided with this repository.

---

## Acknowledgements
Developed as part of **Inter IIT Tech Meet 14.0** under the **Eternal** problem statement on warehouse automation.
