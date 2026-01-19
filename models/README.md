## Contents

The repository's models directory should contain:

- Trained TensorFlow / Keras models (e.g., `.h5`, SavedModel directories)
- TensorFlow Lite models (`.tflite`) optimized for Raspberry Pi / edge inference
- Label files (e.g., `labels.txt`, `classes.json`) that map class indices to names
- Metadata and reports:
  - training logs
  - accuracy / evaluation reports
  - config files used for training (hyperparameters, dataset splits)
- Optional assets:
  - sample test images
  - preprocessing scripts

## Model Workflow

1. Capture frames from the Pi Camera.
2. Preprocess frames (resize, normalize, convert color space if needed).
3. Run inference using the deployed model (TensorFlow Lite on the Pi for low-latency).
4. Obtain class probabilities and confidence scores.
5. Apply decision logic and thresholding to decide whether deterrent actions are required (e.g., alarm, lights, sound).
6. Log detections and optionally upload telemetry.
---

## Deployment Recommendations

- Use TensorFlow Lite models on Raspberry Pi for:
  - Faster inference
  - Lower memory footprint
  - Reduced power consumption
- Prefer quantized models (float16 / int8) for performance when acceptable accuracy trade-offs are met.
- Use hardware acceleration (e.g., Coral TPU) if available for higher throughput.
- Run inference inside a lightweight service/daemon that can:
  - Restart on failure
  - Expose a simple API or socket for the rest of the AgriGuardian system

Example minimal load snippet:
```python
# Load tflite model 
interpreter = tf.lite.Interpreter(model_path="models/tflite/agri_model_v1.tflite")
interpreter.allocate_tensors()
```

---

## Naming & Versioning Conventions

- Include semantic versioning in filenames: `pest_detector_v1.tflite`, `pest_detector_v1.1.tflite`
- Keep a `metadata/` folder with:
  - `training_report_v1.md` — dataset, metrics (precision/recall/F1), evaluation images
  - `config_v1.yaml` — training hyperparameters and preprocessing steps
- Maintain a changelog when models are updated with reasons and metrics.

---

## How to Add or Update a Model

1. Train and evaluate the model; keep a reproducible training config.
2. Export the model in SavedModel format and convert to TensorFlow Lite for deployment.
3. Add:
   - `.tflite` to `models/tflite/`
   - labels to `models/labels/labels.txt`
   - training report and config to `models/metadata/`
4. Update this README (or a changelog) with the new version, expected input shape, and sample accuracy.
5. Run integration tests on a Raspberry Pi (or emulator) to verify end‑to‑end behavior.

Suggested PR checklist:
- [ ] Model file added to `models/tflite/`
- [ ] Labels file added and verified
- [ ] `metadata/training_report_*.md` added
- [ ] Inference test script or integration note included

---

## Testing & Validation

- Keep a small set of labeled test images for quick validation under `models/tests/`.
- Run inference on edge hardware and measure:
  - Latency (ms per frame)
  - CPU / memory utilization
  - Detection accuracy in real-world lighting conditions
- Monitor false positive / false negative rates and tune thresholds accordingly.

---

## Future Improvements

- Multi-class pest detection with expanded taxonomy (birds, rodents, boar, stray dogs, etc.)
- Night-time optimized models (infrared / low-light augmentation)
- Further quantization and pruning for faster inference
- Continual learning pipeline to incorporate new labeled field data
- Automatic model benchmarking and deployment scripts

---
