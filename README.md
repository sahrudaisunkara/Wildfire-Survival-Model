# WiDS 2026 Wildfire Survival Forecasting

This repository contains my solution for the **WiDS Global Datathon 2026**, focused on predicting wildfire risk using early-stage incident data. The objective is to estimate the probability that a wildfire will threaten evacuation zones within 12h, 24h, 48h, and 72h after ignition.

## 🔥 Problem Overview

Emergency responders must prioritize limited resources with incomplete early signals. This project frames the task as a **right-censored survival analysis problem** and produces calibrated multi-horizon probability forecasts to support real-world decision making.

## 📊 Dataset

* 316 wildfire events (221 train / 95 test)
* Features derived from the first 5 hours after ignition
* Growth dynamics, centroid movement, and distance-to-evacuation metrics
* Right-censored time-to-event labels

## 🧠 Modeling Approach

### ✅ Version 4 — Adaptive Hybrid Model 

The final approach combines:

* **XGBoost AFT Survival Model**
  Learns urgency ranking and time-to-event structure.

* **Horizon-Specific Binary Classifiers**
  Improve calibration at each prediction window.

* **Adaptive Horizon Blending**
  Stronger weighting at 48h to align with the competition’s weighted Brier score.

### Key Techniques

* 5-Fold Cross-Validation
* Survival-to-probability transformation
* Adaptive hybrid blending
* Probability smoothing
* Monotonic constraint enforcement

## 📈 Performance

Version 4 achieved a significant improvement on the public leaderboard by enhancing probability calibration while preserving ranking quality.

## 🛠 Tech Stack

* Python
* XGBoost (Survival AFT + Binary)
* Scikit-learn
* NumPy / Pandas

## 🚀 Next Steps

* Advanced calibration refinement
* Ensemble survival strategies
* Robust probability ranking optimization

---

This project demonstrates applied survival modeling and probabilistic forecasting for real-world wildfire risk assessment.
