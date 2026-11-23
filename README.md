# 🤖 Autonomous Line-Follower Robot (mBot2)

<p align="left">
  <img src="https://img.shields.io/badge/Hardware-Makeblock_mBot2-00979D?style=for-the-badge" alt="mBot2" />
  <img src="https://img.shields.io/badge/Controller-CyberPi_(ESP32)-E7352C?style=for-the-badge&logo=espressif&logoColor=white" alt="CyberPi" />
  <img src="https://img.shields.io/badge/IDE-mBlock_5-0284C7?style=for-the-badge" alt="mBlock" />
  <img src="https://img.shields.io/badge/Sensors-Quad_RGB_Line_Follower-10B981?style=for-the-badge" alt="Sensors" />
  <img src="https://img.shields.io/badge/Award-🥈_2nd_Place_Winner-F59E0B?style=for-the-badge" alt="2nd Place" />
</p>

## 📌 Overview
An autonomous mobile robot engineered for the official **mBot2 Robotics Competition** organized by **Robotech Club (FST Tangier)**. The system relies on high-frequency optical line-tracking sensors and real-time differential motor control to navigate straight paths, curves, and sharp turns with optimal speed and stability.

> 🏆 **Competition Achievement:** Awarded **2nd Place** in the official mBot2 Robotics Competition.

---

## 🎯 Key Objectives
- **Autonomous Navigation:** Accurately detect and track a black line on a high-contrast competition track.
- **Speed vs. Stability Optimization:** Maximize traversal speed while preventing overshoot on tight corners.
- **Real-Time Constraint Handling:** Execute closed-loop sensor polling and motor corrections under strict competition time limits.

---

## 🧠 Control Logic & Decision Matrix

The robot operates on a continuous closed-loop feedback cycle, dynamically adjusting left and right encoder motor velocities based on real-time sensor states:

| Sensor State | Track Condition | Control Action | Motor Adjustment |
| :--- | :--- | :--- | :--- |
| **Center Sensor Active** | Robot aligned on line | **Move Forward** | Equal nominal speed on Left & Right motors |
| **Left Sensor Active** | Robot drifting right | **Turn Left** | Reduce Left motor speed / Boost Right motor |
| **Right Sensor Active** | Robot drifting left | **Turn Right** | Boost Left motor speed / Reduce Right motor |
| **Line Lost / Sharp Angle** | High-curvature turn | **Recovery Pivot** | Differential reverse/forward correction until re-locked |

---

## ⚙️ System Workflow

```text
[ Optical Line Sensors ] ──► [ CyberPi Controller (Real-Time Logic) ] ──► [ Differential Motor Speed Control ]
