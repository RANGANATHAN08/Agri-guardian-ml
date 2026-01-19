**🧩 Components Used**
1. Raspberry Pi 4

Acts as the central processing unit

Runs the CNN/TFLite model

Controls sensors and alarms

Handles real-time inference

2. Pi Camera Module

Captures live video feed from the field

Provides input frames for the CNN model

Supports continuous monitoring

3. Alarm & Deterrent System

**Multi-stage deterrent setup:**

Stage	Component	Purpose
1	LED / Flash Light	Visual deterrence

2	Ultrasonic Buzzer	Sound-based deterrence

3	Loud Speaker	Noise repulsion

4	Mechanical Scare Device	Physical deterrence

4. Communication Module (Optional)

GSM / Wi-Fi module

Sends alerts to farmer’s mobile

Used when all deterrent stages fail

5. Power Supply

Battery pack

Solar panel (optional for remote areas)

Enables continuous operation

**🔌 Hardware Workflow**

Camera captures live video

Raspberry Pi processes frames

CNN model performs inference

Decision logic checks confidence

Alarm stages are triggered

Farmer is notified if needed

**📌 Future Enhancements**

Infrared / night-vision camera

Thermal camera integration

Weather-resistant casing

Low-power optimization

Multi-camera setup

