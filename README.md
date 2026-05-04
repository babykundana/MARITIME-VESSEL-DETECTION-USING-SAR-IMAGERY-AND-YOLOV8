# MARITIME-VESSEL-DETECTION-USING-SAR-IMAGERY-AND-YOLOV8
**Project Description**
This project presents a deep learning-based approach for maritime vessel detection using Synthetic Aperture Radar (SAR) imagery. Unlike optical imaging systems, which are affected by fog, clouds, and low-light conditions, SAR enables reliable monitoring under all-weather and day-and-night conditions. The objective is to develop an automated system capable of accurately detecting ships in complex maritime environments.
A pretrained YOLOv8s model is used for object detection due to its lightweight architecture and real-time capability. The model is trained on the HRSID dataset, where vessels are manually annotated using Roboflow with a single class label, “SHIP.”

**Dataset**
1. Dataset: HRSID (High-Resolution SAR Image Dataset)
2. Total images: 1069
3. Class: SHIP
4. Annotation: Manual annotation with augumentation using Roboflow

**Methodology**

The system follows a structured pipeline for vessel detection:

1) SAR image acquisition from the HRSID dataset
2) Manual annotation using bounding boxes
3) Preprocessing by resizing images from 800×800 to 640×640
4) Data augmentation using horizontal and vertical flipping
5) Dataset split into 80% training and 20% validation
6) Training using a pretrained YOLOv8s model
7) Detection output with bounding boxes and normalized YOLO format values

**Algorithm (YOLOv8 Detection Process)**
1) Input SAR image is resized to 640×640 and normalized
2) The image is passed through the CNN backbone to extract features
3) Feature maps from different layers are combined using feature fusion
4) The detection head predicts bounding boxes, confidence scores, and class labels
5) Multiple bounding boxes are generated for potential objects
6) Non-Maximum Suppression (NMS) is applied to remove overlapping duplicate boxes
7) Final output includes bounding boxes with class labels and normalized YOLO coordinates

**Results**

The model detects vessels in SAR images by generating bounding boxes around ships. It achieves the following performance:

. **Precision:** 0.8962
. **Recall:** 0.8417
. **mAP@0.5:** 0.9142

The system performs effectively in challenging conditions such as sea clutter and speckle noise.

**Applications**

1) Maritime surveillance for monitoring large ocean regions
2) Security and defense for detecting illegal activities
3) Navigation safety for reducing collision risks
4) Search and rescue operations for locating vessels

**Tools and Technologies**
Python
YOLOv8 (Ultralytics)
Roboflow
Google colab

**Future Scope**
1) Vessel classification into different ship categories 
2) Integration with AIS data for improved tracking
3) Improved robustness in dense maritime environments
4) Training on larger and more diverse datasets

