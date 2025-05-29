# 🚪 Door-to-Wall Distance Estimator using YOLOv8m and Computer Vision

This project demonstrates how to train a YOLOv8m model to detect doors and walls in floor plan images, even with a very small dataset of just 10 images. After detection, the user can select a door, and the system calculates the distance from the door centroid to the opposite wall, utilizing OCR to detect scale or user input for scale if none is found.

---

## Overview

1. **Model Training**  
   Using only 10 annotated images of floor plans, a YOLOv8m model is trained to accurately detect **doors** and **walls**. Despite the limited data, careful annotation and augmentation ensure good detection performance.

2. **Detection on Input Image**  
   The trained model is applied on new floor plan images to detect doors and walls. Doors are highlighted with green bounding boxes and walls with blue.

3. **User Interaction for Door Selection**  
   Detected doors are numbered on the image. The user inputs the door number to select which door they want to analyze.

4. **Scale Extraction via OCR**  
   The system runs OCR on the image to detect scale annotations like `1cm = 5m`.  
   - If scale text is found, it automatically converts pixel distances to real-world units.  
   - If no scale is found, the user is prompted to input a scale manually (e.g., pixels per cm).

5. **Distance Calculation**  
   The code calculates the distance from the **door centroid** to the **opposite wall** along a perpendicular line to the door’s orientation.

---

## Workflow and Screenshots

### 1. Input Image  
The original floor plan image uploaded by the user.

![Input Image](images/input_image.png)

---

### 2. Detection of Doors and Walls  
Doors are marked in green, walls in blue. Each door is numbered for easy selection.

![Detected Doors and Walls](images/detection_output.png)

---

### 3. Door Selection  
User inputs the door number to select. The selected door centroid is highlighted.

![Door Selection](images/door_selection.png)

---

### 4. Distance Measurement  
A black line is drawn from the door centroid to the opposite wall, and the distance in pixels and real-world units is displayed.

![Distance Measurement](images/distance_measurement.png)

---

## Installation & Usage

### Requirements
- Python 3.8+
- OpenCV
- NumPy
- Ultralytics YOLOv8
- pytesseract (for OCR)
- Other dependencies as per your environment

### Steps

1. **Train the YOLOv8m model**  
   Annotate 10 images with doors and walls, then train YOLOv8m with your dataset.

2. **Run detection**  
   Use the trained model to detect doors and walls on new images.

3. **Select door**  
   View numbered doors and input the door number to analyze.

4. **Scale extraction**  
   OCR runs automatically. If no scale found, input scale manually.

5. **Distance calculation**  
   Distance from door centroid to opposite wall is calculated and shown.

---

## Notes

- Small dataset training requires good augmentation for best results.  
- Scale extraction accuracy depends on clear scale text in images.  
- Distance calculation assumes walls are rectangular bounding boxes.

---

## Contact

For questions or contributions, please open an issue or contact me.

---

