# AI-Powered Sewer Defect Detection & Recommendation System

## Overview

This project introduces a two-stage hybrid AI pipeline designed to automate the inspection and maintenance planning of underground sewer pipelines. By replacing subjective manual reviews of CCTV footage with quantitative metrics, the system identifies structural anomalies and provides data-driven maintenance priorities.

The system achieves high-speed performance, operating at **35 FPS**, making it suitable for real-time edge deployment on robotic crawlers or drones.

## Features

Two-Stage Pipeline: Integrates deep learning for visual recognition and classical machine learning for actionable decision-making.

Multi-Class Detection: Identifies 7 specific defect types: Cracks, Holes, Debris, Buckling, Joint Offset, Utility Intrusion, and Obstacles.

Automated Urgency Scoring: Classifies maintenance needs into **Low, Medium, or High** urgency with **97.2% accuracy**.

Real-Time Processing: Optimized architecture allows for live monitoring during field inspections.

## System Architecture

### Stage 1: Defect Detection (YOLOv8)

Utilizes the **YOLOv8 (You Only Look Once)** framework for high-accuracy localization and classification of defects from image/video frames.

Backbone: Modified CSPDarknet53 for hierarchical feature extraction.

Neck: PANet for multi-scale feature fusion.

Head: Anchor-free decoupled head for predicting bounding boxes and class probabilities.

### Stage 2: Maintenance Recommendation (Random Forest)

A **Random Forest Classifier** analyzes quantitative features extracted from Stage 1 to predict the required maintenance action.

Input Features: Class ID, Confidence Score, and Bounding Box Area (used as a severity proxy).

Output: Actionable strings such as "Urgent action: notify utility/excavate" or "Monitor crack periodically".

## Technical Stack

Language: Python 

Deep Learning: PyTorch, Ultralytics YOLOv8 

Machine Learning: Scikit-learn (Random Forest, LabelEncoder) 

Image Processing: OpenCV, Pillow 

Data Handling: NumPy, Pandas 

Visualization: Matplotlib, Seaborn 

## Performance Results

 Urgency Classification Accuracy : 97.2% 

 Inference Speed : 35 FPS 

 Detection mAP@.5 : 0.65 (across 7 classes) 

 Recommendation Latency : 15 ms 

## Future Work

IoT Integration: Real-time transmission of alerts from autonomous robotic crawlers to centralized dashboards.

Predictive Analytics: Forecasting potential failures by analyzing historical defect trends and pipe metadata.

Multimodal Imaging: Incorporating thermal or infrared data to detect hidden leakages or corrosion.
  
## Contributors

**Maithili A** (NSS22EC070) 

**Swathy V** (NSS22EC120)

**Theertha R** (NSS22EC121) 

**Guide:** Dr. Maya Mohan, Dept. of CSE, NSS College of Engineering 
