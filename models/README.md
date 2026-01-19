**Models Directory**

This folder contains all trained and optimized machine learning models used in the AgriGuardian system.

These models are responsible for detecting wild boars and other pests from real-time camera feeds and triggering the appropriate deterrent actions.

**📁 Contents**

This directory will include:

Trained CNN Models
Deep learning models trained using TensorFlow/Keras for pest and animal detection.

TensorFlow Lite Models (.tflite)
Optimized lightweight versions of trained models for deployment on Raspberry Pi.

Label Files
Mapping of class indices to pest names (e.g., wild_boar, bird, rodent, background).

Model Metadata
Accuracy reports, training logs, and configuration details.

**🔄 Model Workflow**

Images are captured using the Pi Camera

Frames are preprocessed (resize, normalize, etc.)

CNN model performs classification

Output confidence scores are generated

Decision logic triggers the alarm system

**⚙️ Deployment**

The trained TensorFlow Lite model is loaded on the Raspberry Pi for:

Real-time inference

Low-latency performance

Edge-based processing

Reduced power consumption

**🔮 Future Improvements**

Multi-class pest detection models

Night-time optimized models

Quantized models for faster inference

Larger and more diverse training datasets

Improved accuracy under low-light conditions
