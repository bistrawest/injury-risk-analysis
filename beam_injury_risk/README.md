# Gymnastics Beam Injury Risk Analysis

## Project Overview
This project analyzes **injury risk during gymnastics beam routines**.  
It uses a **beam video** as input and performs:

- Pose detection using **MediaPipe**  
- Calculation of **joint angles** and **angular velocities**  
- Flagging of **risky frames** based on extreme joint velocities  
- An **illustrative machine learning model** (Random Forest) to predict risky frames  

> **Note:** The dataset is small and the ML model is illustrative — intended for demonstration, not production use.

## Folder Structure
- `beam_video.mp4` — Input video (optional if large)  
- `injury_risk_analysis.ipynb` — Jupyter notebook with all code and analysis  
- `beam_pose_risk_data.csv` — Generated dataset  
- `requirements.txt` — Python dependencies  
- `README.md` — This file  

## Dependencies
Install required packages:

pip install -r requirements.txt

### Contents of requirements.txt:
- pandas
- numpy
- matplotlib
- scikit-learn
- opencv-python
- mediapipe
- jupyter


---

## Usage 
1. Place your video file in the project folder (or reference an external link).
2. Open and run `injury_risk_analysis.ipynb`.
3. The notebook will:
   - Read video frames
   - Detect pose landmarks
   - Calculate joint angles and angular velocities
   - Flag frames exceeding velocity thresholds as `risky_velocity`
   - Save the dataset to `beam_pose_risk_data.csv`
   - Train an illustrative Random Forest classifier to predict risky frames

---

## Output

The dataset contains:
- Joint angles: left_knee, right_knee, left_hip, right_hip, left_shoulder, right_shoulder (degrees)
- Angular velocities: *_vel for each joint (degrees/frame)
- Risky frames: risky_velocity (0 or 1) indicating extreme angular velocity

---

## Analysis / Visualization

The notebook includes:
- Histograms of joint angles and velocities
- Time-series plots of angular velocities
- Counts of risky frames and joint contributions
- Machine learning demonstration:
   - Random Forest classifier
   - Feature importance visualization

---

## Next Steps / Extensions
- Expand dataset with more videos and gymnasts
- Try other ML models (Logistic Regression, Gradient Boosting, SVM)
- Add video visualization of risky frames
- Explore additional biomechanics features (joint torques, angular acceleration)
