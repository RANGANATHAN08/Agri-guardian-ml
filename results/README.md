# AgriGuardian — Results & Outputs

---

## Contents (what you'll find here)
- Detection screenshots and sample frames
- Bounding box visualizations with confidence overlays
- Sample prediction outputs 
- Performance graphs (accuracy/precision/recall, FPS over time)
- Real-world testing photos and notes
---

## How to read these results
- Screenshots show a prediction frame with bounding boxes and confidence scores.
- Use confidence overlays to determine thresholds for triggering alarms in your deployment.

---

## Model performance (summary)
The CNN-based detector was evaluated across multiple environmental conditions (daylight, dusk, and low-light). Key observed metrics from validation/test runs:

- Accuracy: ~90%
- Precision: ~89%
- Recall: ~94%
- Real-time inference: ~30 FPS (depends on hardware)
- False positives: significantly reduced through post-processing and thresholding

Interpretation:
- High recall (~94%) indicates most pests are detected.
- Precision (~89%) means the majority of detections are correct; remaining false positives can be tuned with thresholds.
- Real-time inference at ~30 FPS supports live deployment on modest edge hardware.

---

## System-level results — alarm stages
The multi-stage alarm system escalates deterrents until the pest is deterred. Typical effectiveness observed during testing:

| Stage | Deterrent Type         | Effectiveness | Notes |
|-------|------------------------|---------------|-------|
| 1     | Visual (LED)           | Moderate      | Low-power; useful as first warning |
| 2     | Ultrasonic sound       | High          | Effective for many insect species |
| 3     | Loud (audible) sound   | Very High     | More disruptive, used if Stage 2 fails |
| 4     | Mechanical scare       | Maximum       | Physical movement / actuator; last resort |

In the majority of test scenarios pests were deterred before reaching Stage 4.

---

## Visual outputs
This folder includes:
- Sample detection frames annotated with bounding boxes and class/confidence labels
- Confidence score heatmaps / overlays
- Snapshots captured during alarm triggers
- Live stream captures demonstrating system operation

These visuals are intended for quick verification and for presentations or reports.

---


## Future result additions (planned)
- Night-time detection results (low-light evaluation)
- IR camera outputs and evaluations
- Multi-pest classification test results
- Field deployment images and long-term performance logs
- Comparative charts for different model variants / thresholds

---

## How to regenerate or add results
1. Run the evaluation script (see repository root for evaluation scripts) on the chosen dataset.
2. Save visual frames to `results/visuals/` with clear filenames and timestamps.
3. Append alarm logs to `results/logs/` and prediction summaries to `results/predictions/`.
4. Commit new artifacts with descriptive messages, and update this README if you add new result types.

---

