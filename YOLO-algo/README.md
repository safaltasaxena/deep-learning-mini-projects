# 🔍 Object Detection Basics (YOLO)

## ❓ Problem
Image classification only tells what object is present.
Real images contain multiple objects and multiple people,
so we need to detect what the object is and where it is.

Challenges:
• Multiple objects in one image  
• Overlapping bounding boxes  
• Duplicate detections  

## ✅ Solution
YOLO-style object detection predicts bounding boxes and
class probabilities in a single forward pass.

The image is divided into grid cells, and each grid cell
predicts multiple bounding boxes to handle multi-object
and multi-person scenarios.

## 📘 Concepts Covered
• Object localization  
• Multi-object & multi-person detection  
• Grid-based image partitioning  
• Multiple bounding boxes per grid cell  
• Intersection over Union (IoU)  
• Non-Maximum Suppression (NMS)  
• Combining bounding box vectors  

## 🎯 Purpose
To build a strong conceptual foundation in object detection
before implementing and training full YOLO models.
