# AAE4011 Assignment 1 — Q3: ROS-Based Vehicle Detection from Rosbag

> **Student Name:** [Lee Hon Yan] | **Student ID:** [25025876D] | **Date:** [17/3/2026]

---

## 1. Overview

*Briefly describe what this project does (1–2 sentences).*
This project implements a ROS-based pipeline that extracts images from a provided rosbag file, performs real-time vehicle detection using a deep learning model, and visualizes the results through a custom User Interface.

## 2. Detection Method *(Q3.1 — 2 marks)*

*Explain the detection model/architecture you chose (e.g., YOLOv5, SSD, Faster R-CNN) and why you selected it.*
Architecture: YOLOv5 uses a backbone network for feature extraction and a decoupled head for predicting bounding boxes and class probabilities.


Why Selected: It offers a superior balance between inference speed and mean Average Precision (mAP), making it ideal for the real-time constraints required in Unmanned Autonomous Systems (UAS) applications.

## 3. Repository Structure

*Show your ROS package file layout (package.xml, CMakeLists.txt, launch files, scripts, etc.).*

## 4. Prerequisites

*List required software and dependencies (OS, ROS version, Python version, key libraries).*
OS: Ubuntu 20.04 LTS


ROS Version: ROS Noetic 

Python: 3.8+


Key Libraries: OpenCV, PyTorch, Ultralytics (YOLO), bagpy

## 5. How to Run *(Q3.1 — 2 marks)*

*Provide clear, step-by-step instructions:*

Clone the repository: git clone [Your-Repository-Link].
install dependencies: pip install ultralytics opencv-python
Build the ROS package: Navigate to your workspace and run catkin_make.
Place the rosbag file: Ensure the downloaded .bag file is in the data/ folder.
Launch the pipeline: roslaunch vehicle_detection_pkg detection.launch.

## 6. Sample Results

*Include:*
- Image extraction summary (total frames, resolution, topic name)
- Detection results (sample screenshot, detection statistics)

## 7. Video Demonstration *(Q3.2 — 5 marks)*


**Video Link:** [YouTube (Unlisted)](https://youtu.be/your-link-here)

*The video (1–3 min) should show:*
- (a) Launching the ROS package
- (b) The UI displaying detection results
- (c) A brief explanation of the results

## 8. Reflection & Critical Analysis *(Q3.3 — 8 marks, 300–500 words)*

### (a) What Did You Learn? *(2 marks)*

*Identify at least two specific technical skills or concepts you gained.*
ROS-Bag Manipulation: I learned how to programmatically interface with .bag files to synchronize image topics with detection timestamps.


Deep Learning Integration: I developed the ability to wrap a pre-trained PyTorch model into a standard ROS node, facilitating real-time communication between the model and visualization tools

### (b) How Did You Use AI Tools? *(2 marks)*

*Describe how you used AI assistants. Discuss both benefits and limitations. If you did not use any, explain your alternative approach.*
i utilized Gemini to assist with debugging the Python-ROS wrapper and generating the CMakeLists configuration.

Benefits: It significantly accelerated the process of troubleshooting ROS environment errors and drafting documentation.

Limitations: Although the AI provided a strong starting point, I initially failed to get the package to build because the AI suggested deprecated ROS commands. I had to manually cross-reference the official documentation to correct the package.xml dependencies.

### (c) How to Improve Accuracy? *(2 marks)*

*Propose two concrete strategies to improve detection accuracy and explain why each would help.*

Fine-tuning on Aerial Datasets: Accuracy could be improved by fine-tuning the model on datasets like VisDrone, as standard YOLO models are often trained on ground-level perspectives rather than UAV top-down views.

### (d) Real-World Challenges *(2 marks)*

*Discuss two challenges of deploying this pipeline on an actual drone in real time.*
Dynamic Lighting and Motion Blur: failure in detection accuracy during fast camera movements in the rosbag. In the real world, drone vibrations and rapid altitude changes create motion blur that requires faster shutter speeds or more robust data augmentation during training.

## 9. References

*List any references, libraries, or datasets used.*
