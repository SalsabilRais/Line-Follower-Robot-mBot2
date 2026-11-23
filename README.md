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

> **[ Optical Line Sensors ]** ──► **[ CyberPi Controller (Real-Time Logic) ]** ──► **[ Differential Motor Speed Control ]**

---

## ⚠️ Engineering Challenges & Solutions
- **Speed vs. Tracking Precision:** Balanced PWM motor power to maintain high velocity on straightaways without losing line lock during sharp turns.
- **Ambient Lighting Sensitivity:** Calibrated sensor thresholds to prevent false readings caused by varying competition room lighting.
- **Rapid Prototyping Under Pressure:** Iteratively tuned turning coefficients within strict competition time constraints.

---

## 📸 Project Gallery

<img width="804" height="1050" alt="PIC3" src="https://github.com/user-attachments/assets/8deb1f2f-f434-48b2-bc2d-9160eb224a47" />
<img width="872" height="1600" alt="PIC2" src="https://github.com/user-attachments/assets/44ecdc48-60d1-4fe1-ba19-08283faee182" />
<img width="836" height="1117" alt="PIC1" src="https://github.com/user-attachments/assets/44914ab0-7257-4845-aa8e-c4ed78efb0d4" />

---

## 🚀 Skills Demonstrated
- **Embedded Control Systems:** Closed-loop sensor-to-actuator feedback design.
- **Robotics Programming:** Event-driven and real-time decision logic in mBlock.
- **Teamwork & Competitive Engineering:** Rapid debugging, hardware calibration, and execution under pressure.

---

## 👩‍💻 Author
**Salsabil Rais** — Embedded Systems & IoT Student (FST Tangier)  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/salsabil-rais)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/SalsabilRais)
