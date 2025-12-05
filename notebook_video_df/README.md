# Gymnastics Beam Injury Risk Analysis

## Project Overview

This project analyzes injury risk during gymnastics beam routines. Using the beam video (beam_video.mp4) as input, the pipeline detects human pose landmarks, calculates joint angles and angular velocities, and flags frames that may correspond to risky movements.

A small dataset is generated from the video, which is then used in an illustrative machine learning example to predict risky frames using joint angles.

---

## Folder Structure

injury_risk_analysis/
|
    beam_pose.ipynb              # Jupyter notebook
    beam_pose_risk_data.csv      # Output dataset
    beam_video.mp4               # Input video (optional if large, see note)
    README.md                    # This README file
    requirements.txt             # Python dependencies
|

---

## Dependencies

Install the required packages with:

pip install -r requirements.txt

Contents of requirements.txt:

pandas
numpy
matplotlib
scikit-learn
opencv-python
mediapipe
jupyter


---

## Usage
1.	Place your video file in the project folder (or reference an external link).
2.	Open and run the notebook injury_risk_analysis.ipynb.
3.	The notebook will:
	• 	Read the video frame by frame
	•	Detect pose landmarks using MediaPipe
	•	Calculate joint angles and angular velocities
	•	Flag frames exceeding a velocity threshold as risky_velocity
	•	Save the resulting dataset to beam_pose_risk_data.csv
	•	Optionally train an illustrative ML model (Random Forest) to predict risky frames

---

## Output

The CSV file beam_pose_risk_data.csv contains:

Column	Description
left_knee	Angle of the left knee (degrees)
right_knee	Angle of the right knee (degrees)
left_hip	Angle of the left hip (degrees)
right_hip	Angle of the right hip (degrees)
left_shoulder	Angle of the left shoulder (degrees)
right_shoulder	Angle of the right shoulder (degrees)
*_vel	Angular velocity of each joint (degrees/frame)
risky_velocity	Flag (0 or 1) indicating frames with high angular velocity

Note: This is a small dataset, generated from a single video, and the ML model is illustrative only, intended to demonstrate machine learning concepts rather than produce a deployable predictor.

---

## Analysis / Visualization

The notebook includes:
	• Histograms of joint angles and velocities
	• Time-series plots of angular velocities over frames
	• Counts of risky frames and joint contributions
	• Machine learning demonstration: Random Forest classifier with feature importance

---

## Next Steps / Extensions
	• Expand dataset with multiple videos or gymnasts
	• Test other ML models (Logistic Regression, Gradient Boosting, SVM)
	• Integrate video visualization of risky frames
	• Use more advanced biomechanics features (joint torques, angular acceleration)
