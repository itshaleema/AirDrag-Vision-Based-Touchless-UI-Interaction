# AirDrag-Vision-Based-Touchless-UI-Interaction
# Haleema Iftikhar

## Abstract

**AirDrag** is a real-time computer vision system enabling users to interact with virtual elements using natural hand gestures, specifically pinch-based dragging. The system utilizes a monocular webcam and applies hand landmark detection via [MediaPipe Hands], wrapped through [cvzone]'s high-level interface. This project demonstrates a lightweight, hardware-independent interface prototype that aligns with current research trends in **Human-Computer Interaction (HCI)**, **wearable interfaces**, and **touchless control for robotics and IoT systems**.

---

## Motivation

The need for intuitive, non-contact interaction modalities has increased with the rise of **wearable technology**, **robotics**, and **public interactive systems**, particularly in health-sensitive environments. Vision-based gesture control offers a cost-effective and scalable solution, eliminating the need for physical sensors or controllers. This project aims to demonstrate such interaction through a proof-of-concept prototype that leverages fingertip-based control to manipulate on-screen objects.

---

## System Overview

### ✋ Hand Detection

The system uses **MediaPipe Hands** (via `cvzone.HandTrackingModule`) to detect a single hand and extract 21 hand landmarks. These landmarks are used to compute distances between key fingers to identify a **pinch gesture** (index and middle finger tips).

### 📦 UI Interaction

When a pinch is detected inside any of the virtual boxes, the box follows the fingertip, simulating a drag-and-drop mechanism. The user can interact with multiple boxes independently using the same gesture logic.

### 💡 Use Cases

- Human-Computer and Human-Robot Interfaces  
- Touchless Control in Embedded and IoT Devices  
- Wearable Gesture Systems  
- AR/VR Interface Prototyping  
- Assistive Technologies for Accessibility  

---

## Implementation Details

- **Language:** Python 3.9+
- **Libraries:** OpenCV, NumPy, cvzone (MediaPipe backend)
- **Hardware:** Any standard webcam (no depth camera required)
- **Gesture Detection Logic:**  
  - A **pinch gesture** is considered active when the distance between the index fingertip (`lm[8]`) and the middle fingertip (`lm[12]`) is below a calibrated threshold.
  - Dragging occurs only while pinching inside a defined rectangular region.
  - Rectangle updates are smoothed for natural interaction.

---
Thank You!!!
