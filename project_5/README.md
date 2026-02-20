# 😄 Emotion Detection System — OpenCV + Deep Learning

> Real-time facial emotion recognition using a pre-trained Keras model and OpenCV Haar Cascade, built with Python.

![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=flat&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=flat&logo=opencv&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey?style=flat)
![Status](https://img.shields.io/badge/Status-Working-brightgreen?style=flat)

---

## 🎯 What It Does

This project uses your webcam to detect faces in real time and predict the **emotion** on each face using a deep learning model. It draws a color-coded bounding box and label with confidence % around every detected face — live, frame by frame.

**Detects 7 emotions:**

| Emoji | Emotion  |
|-------|----------|
| 😠    | Angry    |
| 🤢    | Disgust  |
| 😨    | Fear     |
| 😄    | Happy    |
| 😢    | Sad      |
| 😲    | Surprise |
| 😐    | Neutral  |

---

## ✨ Features

- 🎥 **Live webcam feed** — real-time video processing frame by frame
- 🧠 **Deep learning emotion prediction** — pre-trained Keras CNN model (`emotion_model.hdf5`)
- 🟩 **Color-coded bounding boxes** — each emotion gets a unique color
- 📊 **Confidence score** — e.g. `Happy (94.3%)`
- 🔢 **Live face counter** — total faces detected shown on screen
- 📷 **Save snapshot** — press `s` to capture and save current frame
- ❌ **Clean exit** — press `q` to quit and release all resources

---

## 🗂️ Project Structure

```
emotion-detection/
│
├── emotion_detection.py                 # Main script — run this
├── emotion_model.hdf5                   # Pre-trained Keras CNN model
├── haarcascade_frontalface_default.xml  # OpenCV face detector
└── README.md                            # This file
```

> ⚠️ All four files must be in the **same folder** before running.

---

## ⚙️ Setup & Installation

> ⚠️ **Use Python 3.11 only** — newer versions (3.12+) are not fully compatible with TensorFlow/Keras used in this project.

---

### Step 1 — Install Python 3.11

Download from: https://www.python.org/downloads/release/python-3110/

Verify after install:
```bash
python3.11 --version
```

---

### Step 2 — Create a Virtual Environment

```bash
python3.11 -m venv ai_env
```

---

### Step 3 — Activate the Virtual Environment

```bash
# macOS / Linux
source ai_env/bin/activate

# Windows
ai_env\Scripts\activate
```

You should see `(ai_env)` appear at the start of your terminal line.

---

### Step 4 — Install Required Packages

```bash
pip install opencv-python tensorflow keras numpy
```

---

### Step 5 — Run the Project

```bash
python3 emotion_detection.py
```

---

## 🔁 Every Time You Want to Run

> You **must activate** the virtual environment first, then run the script.

```bash
# Step 1 — Activate
source ai_env/bin/activate       # macOS / Linux
ai_env\Scripts\activate          # Windows

# Step 2 — Run
python3 emotion_detection.py
```

---

## 🎮 Controls

| Key | Action |
|-----|--------|
| `s` | Save current frame as `emotion_capture.jpg` |
| `q` | Quit and close the window |

---

## 🧠 How It Works

| Step | Description |
|------|-------------|
| **1. Load Models** | Loads Haar Cascade for face detection + Keras CNN for emotion classification |
| **2. Capture Frame** | Reads live frames from the webcam |
| **3. Detect Faces** | `detectMultiScale()` locates all faces in the grayscale frame |
| **4. Preprocess ROI** | Each face is cropped, resized to **48×48**, normalized to `[0, 1]` |
| **5. Predict Emotion** | Model outputs softmax probabilities for all 7 emotion classes |
| **6. Display Result** | Color-coded box + emotion label + confidence % drawn on frame |

---

## 📦 Dependencies

| Package | Purpose |
|---------|---------|
| `opencv-python` | Webcam access, face detection, drawing on frames |
| `tensorflow` | Loading and running the deep learning model |
| `keras` | High-level model API |
| `numpy` | Image array preprocessing |

---

## 🔧 Troubleshooting

| Problem | Fix |
|---------|-----|
| `Error: No webcam found` | Try changing `VideoCapture(0)` to `1` or `2` |
| `Cannot load model` | Make sure `emotion_model.hdf5` is in the same folder |
| `Cannot load cascade` | Make sure `haarcascade_frontalface_default.xml` is in the same folder |
| TensorFlow install fails | Make sure you're using **Python 3.11** inside the virtual environment |
| Wrong emotions / low accuracy | Improve lighting and face the camera directly |
| Windows camera blocked | Settings → Privacy & Security → Camera → Enable for Desktop apps |

---

## 🚀 Possible Improvements

- [ ] Add age and gender detection
- [ ] Show a real-time emotion bar chart alongside the video
- [ ] Record and export annotated video
- [ ] Build a GUI using Tkinter or PyQt
- [ ] Replace Haar Cascade with DNN-based face detector for better accuracy
- [ ] Deploy as a web app using Flask + WebSockets

---

## 📚 Concepts Used

- **OpenCV** — Computer vision, webcam capture, drawing utilities
- **Haar Cascade Classifier** — Fast face detection using pre-trained XML model
- **Convolutional Neural Network (CNN)** — Deep learning model trained on the FER dataset
- **FER Dataset** — 7-class facial emotion recognition dataset (48×48 grayscale)
- **Softmax Output** — Converts model output into probabilities for each emotion class
- **Virtual Environment** — Isolated Python environment to avoid package conflicts

---

## 📬 Contact

Made by **Bishal Bhowmik** · B.Sc Computer Science · Haldia Institute of Management

[![GitHub](https://img.shields.io/badge/GitHub-B--2005-181717?style=flat&logo=github)](https://github.com/B-2005)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Bishal%20Bhowmik-0A66C2?style=flat&logo=linkedin)](https://www.linkedin.com/in/bishal-bhowmik-998504394/)

---

*Built with Python 3.11, OpenCV & TensorFlow/Keras · Mentored by SK Sahil (Code_ScholarEU)*
