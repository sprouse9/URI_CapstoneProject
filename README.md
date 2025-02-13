# URI DSP 577 Capstone Research Project by Randy Sprouse

## Project Summary  
This project focuses on **car detection and tracking** using a dataset of **500 images** labeled in the **YOLO annotation format**.  
The goal is to develop a **machine learning model** capable of accurately detecting vehicles in real-world driving conditions.  

The dataset consists of **still frames of cars driving through a section of road**, each with corresponding annotation files containing **bounding box coordinates** for detected vehicles.  

This project will involve:  
✅ **Pre-processing the dataset**  
✅ **Fine-tuning a pre-trained YOLO model**  
✅ **Evaluating detection accuracy using IoU, mAP, and precision-recall metrics**  
✅ (Optional) Implementing **object tracking** if time permits  
✅ (Optional) Tests Model Robustness – How well does it handle different lighting conditions, camera angles, and vehicle types from my own traffic photos.

---

## Dataset Properties  
The **Car Detection dataset** consists of a sequence of **500 still frames** captured from a road scene.  
- **Format:** Each frame is stored as a **JPG image** with a corresponding **TXT annotation file**.  
- **Annotations:** Each `.txt` file contains multiple lines, where each line represents a detected car's **bounding box coordinates** using the **YOLO annotation format**.  

```
📂 train/  
├── 📁 images/  
│     ├── 🖼 frame_0000.jpg   
│     ├── 🖼 frame_0001.jpg   
│     ├── 🖼 frame_0002.jpg   
│     ├── 🖼 frame_0003.jpg   
├── 📁 labels/   
│   ├── 📜 frame_0000.txt
│   ├── 📜 frame_0001.txt
│   ├── 📜 frame_0002.txt
│   ├── 📜 frame_0003.txt
```

### **YOLO Label Format (Normalized)**
Each line in the `.txt` annotation file follows this structure:  

```plaintext
<class_id> <x_center> <y_center> <width> <height>
```

* class_id = 0 → Represents a car object
* x_center, y_center → Bounding box center (normalized to [0,1])
* width, height → Bounding box size (relative to image dimensions)

Example Annotation File (frame_0001.txt):

```
0   0.494271   0.479630   0.070833   0.162963
0   0.296094   0.050000   0.021354   0.031481
0   0.237500   0.137963   0.032292   0.059259
0   0.207292   0.453241   0.073958   0.125000
0   0.463542   0.322685   0.052083   0.110185
0   0.121805   0.989421   0.061891   0.021157
0   0.332031   0.247685   0.042188   0.084259
0   0.319531   0.019907   0.017188   0.028704
0   0.290885   0.131481   0.030729   0.051852
```

Example Frame from Dataset  
Below is an example of a single frame (frame_0001.jpg) from the dataset:  

![Carframe](https://github.com/sprouse9/URI_CapstoneProject/blob/main/images/exampleframe.jpg)

## Model & Implementation
1. Pre-trained Model Selection
This project leverages YOLOv5/YOLOv8 as a base model, which has been pre-trained on the COCO dataset. Fine-tuning will be performed on the car detection dataset to improve accuracy.

YOLO includes various levels of pre-trained models.  
**YOLOv8s** is the small version of YOLOv8, a lightweight model designed for speed and efficiency while maintaining decent accuracy.  
It is pre-trained on the COCO dataset and can be used for object detection, segmentation, and classification tasks.  
The "s" in yolov8s stands for small, indicating that it's optimized for performance on edge devices or situations where computational resources are limited.  
YOLOv8 comes in multiple sizes, balancing accuracy and speed. The variations are:  

| Model | Parameters | FLOPs (B) | Speed (ms) | Use Case |
| --- | --- | --- | --- | --- |
| **YOLOv8n** (nano) | ~3.2M | 8.7 | Fastest | Best for real-time applications on low-power devices |
| **YOLOv8s** (small) | ~11.2M | 28.6 | Fast | Good balance of speed and accuracy |
| **YOLOv8m** (medium) | ~25.9M | 78.9 | Moderate | More accurate but slower |
| **YOLOv8l** (large) | ~43.7M | 165.2 | Slower | Higher accuracy for more complex tasks |
| **YOLOv8x** (extra-large) | ~68.2M | 257.8 | Slowest | Best for high-accuracy tasks on powerful GPUs |






2. Steps to Train the Model   
✅ Dataset Preprocessing: Splitting data into training (80%) and testing (20%)   
✅ Fine-tuning YOLO: Using transfer learning to adapt the model to car detection   
✅ Training & Validation: Evaluating performance using IoU, Precision, Recall, and mAP   
✅ (Optional) Object Tracking Integration using DeepSORT/SORT   

## Evaluation Metrics
The effectiveness of the model will be measured using the following metrics:

* Intersection over Union (IoU): Measures how well the predicted bounding boxes overlap with ground truth
* Mean Average Precision (mAP): Measures overall object detection performance
* Precision & Recall: Evaluates the model's ability to correctly detect vehicles
* Inference Speed: Frames per second (FPS) performance


## Results & Findings
(📌 This section will be updated with final results, sample detections, and accuracy metrics after training is completed.)

## Installation & Usage
To run this project locally:

1. Clone the Repository
```
git clone https://github.com/sprouse9/URI_CapstoneProject.git
cd URI_CapstoneProject
```


