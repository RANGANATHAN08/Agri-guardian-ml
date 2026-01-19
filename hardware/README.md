
## Components

- **Raspberry Pi 4**
  - Central processing unit.
  - Runs the CNN / TFLite model and handles real-time inference.
  - Controls sensors, alarm/deterrent outputs, and network communication.

- **Pi Camera Module**
  - Captures live video frames for the CNN model.
  - Supports continuous monitoring. For night operation, use an IR or night-vision camera.

- **Alarm & Deterrent System**
  - Multi-stage deterrent setup that escalates from visual to mechanical responses.

  | Stage | Component               | Purpose                 |
  |-------|-------------------------|-------------------------|
  | 1     | LED / Flash Light       | Visual deterrence       |
  | 2     | Ultrasonic Buzzer       | Sound-based deterrence  |
  | 3     | Loud Speaker            | Noise repulsion         |
  | 4     | Mechanical Scare Device | Physical deterrence     |

- **Communication Module (Optional)**
  - GSM or Wi‑Fi module to send alerts to the farmer's mobile phone or cloud service.
  - Used as a final notification method if local deterrents fail.

- **Power Supply**
  - Battery pack (recommended: UPS HAT or rechargeable battery bank).
  - Optional solar panel + charge controller for remote deployments.
  - Consider power budgeting for Pi, camera, and deterrent devices.

## Hardware Workflow

1. The Pi Camera continuously captures frames from the field.  
2. The Raspberry Pi preprocesses frames and runs the CNN / TFLite model for detection.  
3. The decision logic evaluates detections and confidence scores.  
4. If an intrusion or target is detected, the system triggers deterrent stages sequentially.  

## Suggested Wiring & Integration Notes

- Use a proper power supply capable of delivering stable 5V at 3A (or a Pi UPS) to the Raspberry Pi 4.  
- Connect the Pi Camera using the ribbon cable to the CSI port; enable the camera interface in Raspberry Pi OS.  
- Drive high-current devices (speakers, mechanical scare devices) through a relay board or MOSFETs — do NOT drive them directly from GPIO pins.  
- Use level shifting or appropriate drivers when interfacing with 12V devices.  
- Add fuses and transient protection for outdoor deployments.

## Power Optimization Tips

- Disable unused services on the Pi to reduce CPU load and power consumption.  
- Use TFLite models optimized for edge devices to lower inference time and energy use.  
- Consider duty cycling the camera or entering low-power modes during idle periods.

## Deployment & Environmental Considerations

- Use a weather-resistant or IP-rated enclosure for outdoor use.  
- Mount the camera at a height and angle that maximizes field-of-view while reducing false positives.  
- Add an IR illuminator or IR-capable camera for night operation.  
- For larger areas, use a multi-camera setup and distributed Pis, or a camera switcher.

## Future Enhancements

- Infrared / night-vision camera integration.  
- Thermal camera integration for robust detection in poor lighting or fog.  
- Full solar-power + power management for long-term remote operation.  
- Mechanical design improvements for faster actuation of scare devices.  
- Low-power hardware variants or microcontroller-based pre-filtering to reduce Pi wake-ups.

