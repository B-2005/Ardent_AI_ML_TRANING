# 🎯 Face Detection System — OpenCV + Python

> Real-time face detection using a webcam and Haar Cascade classifier, built with OpenCV.

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=flat&logo=opencv&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-macOS%20%7C%20Linux%20%7C%20Windows-lightgrey?style=flat)
![Status](https://img.shields.io/badge/Status-Working-brightgreen?style=flat)

---

## 📸 What It Does

This project uses your computer's webcam to detect human faces **in real time**. It draws a green rectangle around each detected face and displays a live count of faces on screen. You can also capture and save a snapshot with a single keypress.

---

## ✨ Features

- 🔴 **Live webcam feed** — real-time video processing frame by frame
- 🟩 **Face bounding boxes** — green rectangles drawn around every detected face
- 🔢 **Live face counter** — displays the number of faces detected on screen
- 📷 **Save snapshot** — press `s` to capture and save the current frame as a `.jpg`
- ❌ **Clean exit** — press `q` to quit and release all resources properly

---

## 🧠 How It Works

| Step | Description |
|---|---|
| **1. Load Model** | Loads OpenCV's pre-trained `haarcascade_frontalface_default.xml` Haar Cascade classifier |
| **2. Capture Video** | Opens the webcam using `cv2.VideoCapture` |
| **3. Grayscale Convert** | Each frame is converted to grayscale for faster, more accurate detection |
| **4. Detect Faces** | `detectMultiScale()` scans the frame for faces using the cascade model |
| **5. Draw & Display** | Rectangles and face count are drawn on the frame and shown in a live window |

---

## 🗂️ Project Structure

```
face-detection/
│
├── face_detection.py       # Main script — run this
├── requirements.txt        # Dependencies
└── README.md               # This file
```

> **Note:** The Haar Cascade XML model (`haarcascade_frontalface_default.xml`) is bundled with OpenCV — no manual download needed.

---

## ⚙️ Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/your-username/face-detection.git
cd face-detection
```

### 2. (Optional) Create a virtual environment
```bash
python3 -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate           # Windows
```

### 3. Install dependencies
```bash
pip install opencv-python
```

---

## ▶️ Running the Project

```bash
python3 face_detection.py
```

The webcam window will open. Point your camera at a face to see detection in action.

---

## 🎮 Controls

| Key | Action |
|---|---|
| `s` | Save current frame as `captured_face.jpg` |
| `q` | Quit and close the window |

---

## 🔧 Configuration

You can tweak these parameters inside `face_detection.py` to adjust detection sensitivity:

```python
faces = face_cascade.detectMultiScale(
    gray,
    scaleFactor=1.3,    # How much image is scaled down per step (lower = more sensitive)
    minNeighbors=5      # Higher = fewer false positives, lower = more detections
)
```

**Webcam index** — if your default camera isn't working, change the device index:
```python
cap = cv2.VideoCapture(0)   # 0 = default camera, 1, 2... for external cameras
```
> The current script uses index `2` with `cv2.CAP_AVFOUNDATION` (macOS). Change to `0` for most systems.

---

## 📦 Dependencies

| Package | Purpose |
|---|---|
| `opencv-python` | Computer vision — webcam access, image processing, face detection |

Install via:
```bash
pip install opencv-python
```

---

## 🚀 Possible Improvements

- [ ] Add eye and smile detection using additional Haar cascades
- [ ] Draw face labels or IDs for multiple faces
- [ ] Add face blurring / anonymization mode
- [ ] Export a recorded video with detections
- [ ] Upgrade to DNN-based detection (more accurate, handles angles better)

---

## 📚 Concepts Used

- **OpenCV (cv2)** — Open Source Computer Vision Library
- **Haar Cascade Classifier** — A pre-trained ML model for object detection
- **Grayscale conversion** — Reduces computation without losing structural information
- **`detectMultiScale()`** — Detects objects at multiple image scales

---

## 📬 Contact

Made by **Bishal Bhowmik** · B.Sc Computer Science · Haldia Institute of Management

[![GitHub](https://img.shields.io/badge/GitHub-B--2005-181717?style=flat&logo=github)](https://github.com/B-2005)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Bishal%20Bhowmik-0A66C2?style=flat&logo=linkedin)](https://www.linkedin.com/in/bishal-bhowmik-998504394/)

---

*Built with Python & OpenCV · Mentored by SK Sahil (Code_ScholarEU)*
