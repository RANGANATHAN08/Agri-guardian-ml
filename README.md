# Agri-guardian-ml 🌾

An AI-powered smart agriculture system for real-time wild boar and pest detection using deep learning and IoT. This project uses a CNN model deployed on Raspberry Pi to monitor paddy fields and prevent crop damage through a multi-stage automated deterrent system.

## 🚀 Overview

AgriGuardian continuously monitors farmland using a camera and deep learning model, detects threats in real time, and activates deterrent mechanisms to minimize yield loss.

## 🔑 Key Features

- Real-time pest detection using CNN
- Raspberry Pi–based edge deployment
- Multi-stage automated alarm system
- Farmer alert mechanism
- Lightweight TensorFlow Lite model
- High accuracy and low latency

## 🛠 Tech Stack

- Python  
- TensorFlow / Keras  
- TensorFlow Lite  
- OpenCV  
- Raspberry Pi  
- Pi Camera  

## ⚙️ How It Works

1. Live video is captured using Pi Camera  
2. Frames are passed to the CNN model  
3. Pest is detected and classified  
4. Deterrent stages are triggered  
5. Farmer is alerted if needed  

## 📊 Performance

- Accuracy: ~90%  
- Real-time inference (~30 FPS)  
- Reduced false alarms  

## 🔮 Future Improvements

- Night vision / IR camera support  
- Mobile app integration  
- Multi-camera scalability  
- More pest classes