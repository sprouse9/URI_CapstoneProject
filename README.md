# URI_CapstoneProject

# Project Summary





# DATA SET - PROPERTIES

The Car Detection data set is a sequence of 500 still captures (frames) of cars driving through a section of road.
Every frame is stored in as a JPG and has a correspoding TXT file with the coordinates of the “bounding box”
for each car detected in frame. 

![Car Detection](https://github.com/sprouse9/URI_CapstoneProject/blob/main/images/folderstructure.jpg)

Each line represents a car with the coordinates separated by a space:

	<class_id> <x_center> <y_center> <width> <height>

where class_id of 0 represents a car object.  If there were multiple object types, different numbers would represent different classes.
This system of encoding represents the YOLO label format (normalized).

Unlike pixel-based bounding boxes, YOLO uses values between 0 and 1, meaning:
	x_center = 0.5 means the box is centered in the middle of the image.
	width = 1.0 would mean the box spans the entire image width.

Here is a sample YOLO text file:
![YOLOformat](https://github.com/sprouse9/URI_CapstoneProject/blob/main/images/yoloformat.jpg)




Here is a sample frame:

![Carframe](https://github.com/sprouse9/URI_CapstoneProject/blob/main/images/exampleframe.jpg)






# URI DSP 577 Capstone Research Project by Randy Sprouse

## Project Summary  
This project focuses on **car detection and tracking** using a dataset of **500 images** labeled in the **YOLO annotation format**. The goal is to develop a **machine learning model** capable of accurately detecting vehicles in real-world driving conditions.  

The dataset consists of **still frames of cars driving through a section of road**, each with corresponding annotation files containing **bounding box coordinates** for detected vehicles.  

This project will involve:  
✅ **Pre-processing the dataset**  
✅ **Fine-tuning a pre-trained YOLO model**  
✅ **Evaluating detection accuracy using IoU, mAP, and precision-recall metrics**  
✅ (Optional) Implementing **object tracking** if time permits  

---

## Dataset Properties  
The **Car Detection dataset** consists of a sequence of **500 still frames** captured from a road scene.  
- **Format:** Each frame is stored as a **JPG image** with a corresponding **TXT annotation file**.  
- **Annotations:** Each `.txt` file contains multiple lines, where each line represents a detected car's **bounding box coordinates** using the **YOLO annotation format**.  

![Car Detection](https://github.com/sprouse9/URI_CapstoneProject/blob/main/images/folderstructure.jpg)  

### **YOLO Label Format (Normalized)**
Each line in the `.txt` annotation file follows this structure:  

```plaintext
<class_id> <x_center> <y_center> <width> <height>

* class_id = 0 → Represents a car object
* x_center, y_center → Bounding box center (normalized to [0,1])
* width, height → Bounding box size (relative to image dimensions)

Example Annotation File (frame_0001.txt):

```
0 0.494271 0.479630 0.070833 0.162963
0 0.296094 0.050000 0.021354 0.031481
0 0.237500 0.137963 0.032292 0.059259
0 0.207292 0.453241 0.073958 0.125000
0 0.463542 0.322685 0.052083 0.110185
0 0.121805 0.989421 0.061891 0.021157
0 0.332031 0.247685 0.042188 0.084259
0 0.319531 0.019907 0.017188 0.028704
0 0.290885 0.131481 0.030729 0.051852
```