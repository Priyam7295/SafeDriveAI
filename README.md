# Driver Safety Monitoring using Deep Learning

## Overview
This project leverages deep learning-based computer vision models to monitor driver alertness in real-time, enhancing road safety. The system continuously tracks the driver’s face and eye state to detect drowsiness. If the driver’s eyes are closed for two consecutive frames, an alarm is triggered to alert the driver.

Additionally, the project is set to incorporate yawning detection. If the driver exceeds a certain threshold of yawns, an alarm will also be triggered, further promoting driver safety by identifying signs of fatigue early.

## Pipeline

### 1. Face Detection and Bounding Box Generation
The first model uses Multi-task CNN with VGG as the base model to detect faces and generate bounding boxes, enhancing both face detection accuracy and classification. It shares layers for classification and regression tasks, followed by additional shared layers, and finally, task-specific layers for each task. This architecture improves performance compared to a simple CNN by enabling the model to learn more robust features and efficiently handle multiple tasks simultaneously. 

**Dataset**: Created a custom dataset focused on a single-driver perspective and fine-tuned a VGG model on top of it for improved performance.

### 2. Eye Area Cropping
Once the face is detected, the eye regions (left and right) are cropped from the bounding box using the second model for further analysis.

**Dataset**:- https://universe.roboflow.com/eye-ipc47/eye-8qscl

**WORKING DEMO:**
![image](https://github.com/user-attachments/assets/adc92d1d-f98f-4b7a-9368-67e1a5c7a39f)


### 3. Eye State Detection
The third model analyzes the cropped eye area to determine if the eyes are open or closed with 99 percent of accuracy. If the driver’s eyes remain closed for two consecutive frames, an alarm is triggered.

**Dataset**:- https://www.kaggle.com/datasets/akshitmadan/eyes-open-or-closed

<img src="https://github.com/user-attachments/assets/30be898f-b573-4db5-a91a-cfd6e6c86382" width="700"/>
<img src="https://github.com/user-attachments/assets/4df8d22e-e852-49ef-b728-40ea52dc0246" width="300"/>

**WORKING DEMO:**

<img src="https://github.com/user-attachments/assets/edf6873f-fe86-4b79-82ee-f49b977bb460" width="300"/>



---


## Technologies Used

- **Deep Learning Framework**: TensorFlow/Keras
- **Model Architecture**: Multi-task CNN, VGG (Base Model), Feature Extraction, Fine Tuning
- **Libraries**: NumPy, Matplotlib (for visualization), Pandas, OpenCV (cv2), JSON, UUID, Zipfile, OS, PIL (Pillow) (Some more)
- **Programming Language**: Python

