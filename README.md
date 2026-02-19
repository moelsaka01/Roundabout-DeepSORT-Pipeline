# Roundabout-DeepSORT-Pipeline
# Roundabout DeepSORT Pipeline

A modular UAV-based vehicle detection and tracking pipeline using:

- YOLOv8 (object detection)
- DeepSORT-style tracking (Kalman + optional appearance embeddings)
- Support for both video files and image-sequence folders
- Trajectory export, speed estimation, and flow aggregation tools

---

## 🚀 Overview

This project processes aerial traffic footage (drone or high-angle) and produces:

- Frame-by-frame vehicle detections
- Unique track IDs per vehicle
- Per-vehicle trajectory CSV files
- Speed estimation (optional)
- Traffic flow aggregation per time interval
- Annotated video output with bounding boxes and IDs

It is designed to be:

- Modular
- Extensible
- Research-friendly
- Production-ready for experimentation

---

## 📂 Project Structure

# Roundabout DeepSORT Pipeline

A modular UAV-based vehicle detection and tracking pipeline using:

- YOLOv8 (object detection)
- DeepSORT-style tracking (Kalman + optional appearance embeddings)
- Support for both video files and image-sequence folders
- Trajectory export, speed estimation, and flow aggregation tools

---

## 🚀 Overview

This project processes aerial traffic footage (drone or high-angle) and produces:

- Frame-by-frame vehicle detections
- Unique track IDs per vehicle
- Per-vehicle trajectory CSV files
- Speed estimation (optional)
- Traffic flow aggregation per time interval
- Annotated video output with bounding boxes and IDs

It is designed to be:

- Modular
- Extensible
- Research-friendly
- Production-ready for experimentation

---

## 📂 Project Structure

# Roundabout DeepSORT Pipeline

A modular UAV-based vehicle detection and tracking pipeline using:

- YOLOv8 (object detection)
- DeepSORT-style tracking (Kalman + optional appearance embeddings)
- Support for both video files and image-sequence folders
- Trajectory export, speed estimation, and flow aggregation tools

---

## 🚀 Overview

This project processes aerial traffic footage (drone or high-angle) and produces:

- Frame-by-frame vehicle detections
- Unique track IDs per vehicle
- Per-vehicle trajectory CSV files
- Speed estimation (optional)
- Traffic flow aggregation per time interval
- Annotated video output with bounding boxes and IDs

It is designed to be:

- Modular
- Extensible
- Research-friendly
- Production-ready for experimentation

---

## 📂 Project Structure

roundabout-deepsort-pipeline/
│
├── config.yaml
├── requirements.txt
├── README.md
├── LICENSE
├── .gitignore
│
├── src/
│ ├── main.py
│ ├── config_loader.py
│ ├── detectors/
│ │ └── yolo_detector.py
│ ├── trackers/
│ │ └── deepsort_tracker.py
│ ├── pipelines/
├── LICENSE
├── .gitignore
│
├── src/
│ ├── main.py
│ ├── config_loader.py
│ ├── detectors/
│ │ └── yolo_detector.py
│ ├── trackers/
│ │ └── deepsort_tracker.py
│ ├── pipelines/


---

## ⚙️ Installation

### 1️⃣ Create Virtual Environment

```bash
python -m venv .venv
.venv\Scripts\activate



---

## ⚙️ Installation

### 1️⃣ Create Virtual Environment

```bash
python -m venv .venv
.venv\Scripts\activate

### 2️⃣ Install Dependencies
python -m pip install --upgrade pip
python -m pip install -r requirements.txt

### ▶️ Running the Detection & Tracking Pipeline

Update config.yaml:
input_video: "data/Drone/0"   # can be folder OR video file
output_tracks_csv: "outputs/tracks.csv"
output_annotated_video: "outputs/annotated.mp4"

Run:
python -m src.main --config config.yaml

Outputs:

outputs/tracks.csv
outputs/annotated.mp4


📊 Export Trajectories + Compute Flows

Generate per-vehicle trajectories and flow statistics:
python -m src.tools.export_trajectories \
  --tracks outputs/tracks.csv \
  --out_dir outputs/trajectories \
  --fps 25 \
  --meters_per_pixel 0.15 \
  --interval 30
python -m src.tools.export_trajectories \
  --tracks outputs/tracks.csv \
  --out_dir outputs/trajectories \
  --fps 25 \
  --meters_per_pixel 0.15 \
  --interval 30

python -m src.tools.export_trajectories \
  --tracks outputs/tracks.csv \
  --out_dir outputs/trajectories \
  --fps 25 \
  --meters_per_pixel 0.15 \
  --interval 30

Options:
--include car truck → filter specific vehicle classes
--fps → required for time-based analysis
--meters_per_pixel → enables speed estimation
--interval → flow aggregation window in seconds

Generated:
track_<id>.csv
summary.csv
flow_intervals.csv
