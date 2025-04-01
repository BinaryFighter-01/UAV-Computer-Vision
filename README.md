# AI-Powered UAV Object Detection

This repository contains the code, documentation, and resources developed during my internship as an **AI Python Developer** at **Engineering Bay Corporation**. The project focuses on designing and implementing an autonomous Unmanned Aerial Vehicle (UAV) system with real-time object detection capabilities using the YOLO (You Only Look Once) model. This work was submitted as part of my Bachelor of Engineering in Artificial Intelligence and Data Science at Savitribai Phule Pune University.

---

## Project Overview

The primary goal of this project was to develop an intelligent UAV system capable of real-time object detection for navigation and safety. The system leverages advanced computer vision techniques, optimized YOLO models, and full-stack development to achieve reliable performance in dynamic environments.

### Objectives
1. Build a fully functional UAV with integrated hardware and software for autonomous navigation.
2. Develop an advanced object detection system using YOLO, TensorFlow, PyTorch, and OpenCV.
3. Create responsive web interfaces integrated with backend APIs for UAV monitoring and control.
4. Optimize AI models for real-time processing on resource-constrained devices.
5. Bridge theoretical knowledge with practical applications in AI-driven autonomous systems.

### Key Features
- **Real-Time Object Detection:** Utilizes YOLOv8 for fast and accurate identification of objects (e.g., buildings, obstacles, people).
- **UAV Integration:** Seamlessly integrates detection algorithms into UAV workflows.
- **Optimized Performance:** Balances accuracy and efficiency for edge device deployment.
- **Full-Stack Development:** Includes web interfaces and APIs for system monitoring.

---

## Steps to run your YOLOv8 object detection script locally from GitHub:

1. **Clone the Repo:**
   ```bash
   git clone https://github.com/<your-username>/AI-UAV-Object-Detection.git
   cd AI-UAV-Object-Detection/src/detection
   ```

2. **Set Up Environment:**
   - Install Python 3.8+.
   - (Optional) Create a virtual env: `python -m venv venv && venv\Scripts\activate` (Windows) or `source venv/bin/activate` (macOS/Linux).

3. **Install Dependencies:**
   ```bash
   pip install ultralytics opencv-python
   ```

4. **Get Model Weights:**
   - Ensure `yolov8m.pt` is in the folder (auto-downloads on first run) or specify its path.

5. **Save and Run Script:**
   - Save as `detect.py`:
     ```python
     from ultralytics import YOLO
     import cv2
     model = YOLO('yolov8m.pt')
     cap = cv2.VideoCapture(0)  # 0 for webcam, or 'video.mp4' for file
     while True:
         ret, frame = cap.read()
         if not ret: break
         results = model(frame)
         cv2.imshow('YOLOv8 Detection', results[0].plot())
         if cv2.waitKey(1) & 0xFF == ord('q'): break
     cap.release()
     cv2.destroyAllWindows()
     ```
   - Run: `python detect.py`

6. **Interact:**
   - View detections; press `q` to quit.

**Troubleshooting:**
- No webcam? Use a video file.
- Missing modules? Reinstall dependencies.
- Model not found? Check file path or internet connection.

Done!

