# 🚘 Metered Parking Detection with YOLOv8 and SAM

This project explores the integration of **YOLOv8 object detection** and **Segment Anything Model (SAM) segmentation** to develop a prototype system for detecting metered parking availability from traffic camera images.

---

## Project Overview

Modern cities increasingly rely on smart systems for parking management. Yet, finding parking, especially in downtown areas, remains notoriously difficult. Drivers often have to circle around, relying solely on their eyes to hunt for available spots. By the time a space is found, valuable time, gas money, and patience are often wasted; sometimes only to park blocks away from the actual destination.

To address this, we propose a prototype service that can visualize metered parking availability and even predict parking status in real time. This project introduces a computer vision-based approach that detects:
- **Vehicles (cars and trucks)** using **YOLOv8**
- **Parking meters and sidewalks** using **Segment Anything Model (SAM)**

By combining these detections, we can infer whether vehicles are parked next to meters or sidewalks — suggesting a metered parking spot's availability.

---

## Workflow

1. **Load and display a traffic camera image**
2. **Use YOLOv8 to detect vehicles**
3. **Crop regions of interest (around meter areas)**
4. **Use SAM to segment sidewalks, meters, and other objects**
5. **Overlay segmentation masks**
6. **Combine YOLO vehicle detections with SAM segmentations** to isolate cars next to meters and sidewalks
7. **Count and visualize parked cars**

---

## Key Findings

- YOLOv8 reliably detects both moving and stationary vehicles.
- SAM successfully segments sidewalks and parking meters.
- Combining these models improves detection accuracy for **metered parking spots**.
- **Remaining limitation**: moving cars might still be flagged as parked if present near detection zones, addressed via segmentation.

---

## Future Work

- Integrate video stream analysis for real-time parking detection.
- Automate region-of-interest detection (meters, sidewalks).
- Improve parked vs. moving car differentiation using frame-to-frame motion analysis.
- Build a simple frontend or dashboard to visualize live parking availability.