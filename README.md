🔥 Fire Detection System using YOLOv8 with Real-Time Email Alerts
📌 Overview

This project implements a real-time fire detection system using YOLOv8 (You Only Look Once, version 8) and OpenCV. The system detects fire from live video streams (e.g., CCTV, webcam) or video files and automatically sends real-time email alerts to predefined recipients when fire is detected.

The aim is to provide an AI-powered early warning system that can be integrated into smart surveillance, building safety systems, and disaster prevention frameworks.

🚀 Features

Real-time fire detection using YOLOv8

Works with webcam, CCTV feeds, or video files

Automatic email alert system with image snapshot when fire is detected

High accuracy with pretrained YOLOv8 model (custom dataset supported)

Lightweight and deployable on edge devices (Raspberry Pi, Jetson Nano, etc.)

🛠️ Tech Stack

Python 3.8+

YOLOv8 (Ultralytics) – object detection

OpenCV – real-time video processing

smtplib (SMTP) – email alert system

📂 Project Structure
Fire-Detection-YOLOv8-Email-Alert/
│── dataset/                # Fire/Non-Fire dataset (optional for training)
│── runs/                   # YOLOv8 training results
│── fire_detection.py       # Main script for fire detection + email alerts
│── requirements.txt        # Dependencies
│── config.py               # Email + system configuration
│── snapshots/              # Captured images of detected fire
│── README.md               # Project documentation

⚙️ Installation

1️⃣ Clone the repository

git clone https://github.com/your-username/Fire-Detection-YOLOv8-Email-Alert.git
cd Fire-Detection-YOLOv8-Email-Alert


2️⃣ Create a virtual environment (recommended)

python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows


3️⃣ Install dependencies

pip install -r requirements.txt


4️⃣ Install YOLOv8

pip install ultralytics

🧾 Configuration

Update config.py with your email credentials:

EMAIL_SENDER = "your_email@gmail.com"
EMAIL_PASSWORD = "your_app_password"
EMAIL_RECEIVER = "receiver_email@gmail.com"
SMTP_SERVER = "smtp.gmail.com"
SMTP_PORT = 587


⚠️ Note: For Gmail, enable App Passwords or “Allow less secure apps.”

▶️ Usage

Run the fire detection system with webcam:

python fire_detection.py --source 0


Run with a video file:

python fire_detection.py --source "fire_video.mp4"


Train YOLOv8 on custom fire dataset:

yolo detect train data=dataset/data.yaml model=yolov8n.pt epochs=25 imgsz=65000

📧 Email Alerts

When fire is detected:

The system captures a frame (snapshot)

Sends an email with the attached image and alert message

Example email:

Subject: 🚨 Fire Alert Detected!

Fire has been detected in the monitored area.
Please check the attached snapshot for details.

📊 Results

Real-time detection speed ~30 FPS (depends on hardware)

Works in low-light and indoor/outdoor scenarios

Email alert delivery within 2-3 seconds

📖 References

Ultralytics YOLOv8 Docs

OpenCV Documentation

Python smtplib module

