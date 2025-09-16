README: Human Gait Analysis with YOLO Pose
Overview

This project demonstrates how to use computer vision and deep learning-based pose estimation to analyze human gait from video recordings. By combining an iPhone-recorded walking video with a YOLO pose detection model, we extract lower-body joint positions and compute biomechanical and spatiotemporal gait metrics.

This workflow is designed for undergraduate students in kinesiology, biomechanics, or computer science who are interested in applying computer vision to real-world human movement analysis.

Objectives

The code aims to:

Normalize video input (iPhone .MOV → .mp4) so it can be processed consistently in Google Colab.

Detect human pose keypoints using YOLOv8 Pose (hip, knee, ankle, etc.).

Compute biomechanical features:

Hip, knee, and ankle joint angles.

Smoothed time-series of joint motion.

Identify gait cycle events:

Heel strike (HS)

Toe strike (TS)

Heel off (HO)

Toe off (TO)

Quantify gait metrics:

Walking cadence (steps per minute).

Average durations of stance, swing, loading response, and push-off phases.

Visualize and export data:

Save annotated plots of joint angles and gait events.

Write CSV files of joint kinematics, key events, and raw keypoints.

Create an annotated video overlaying the skeleton and event labels.

Why This Matters

Gait analysis is a central topic in biomechanics, rehabilitation science, and sports performance. Traditional gait labs rely on expensive motion capture systems; here we demonstrate a low-cost, computer-vision-based approach using widely available tools (a smartphone camera and open-source models).

Students gain exposure to:

Practical use of deep learning for pose estimation.

Translating raw pose keypoints into biomechanically meaningful variables.

Signal processing techniques (smoothing, peak detection).

The connection between movement science and machine learning.

How It Works

Input Video

Upload an iPhone .MOV or .mp4.

The script normalizes it (fixes rotation, scales, converts to H.264, sets 30 fps).

Pose Estimation

YOLOv8 pose detects 17 COCO keypoints.

Lower-body landmarks (hips, knees, ankles) are extracted per frame.

Joint Angles

Hip angle: shoulder–hip–knee.

Knee angle: hip–knee–ankle.

Ankle angle: knee–ankle vs. horizontal reference (approximate dorsiflexion/plantarflexion).

Event Detection

Based on ankle vertical motion and velocity profiles.

Detects HS, TS, HO, and TO frames.

Gait Metrics

Cadence: derived from heel strike intervals.

Phase durations:

Stance (HS→TO)

Swing (TO→HS)

Loading response (HS→TS)

Push-off (HO→TO)

Outputs

CSV files: joint angles, raw keypoints, gait events.

Plots: angles + event markers over time.

Annotated video: skeleton + event labels.

Requirements

Run in Google Colab (GPU recommended).

Dependencies: ultralytics, opencv-python, numpy, scipy, matplotlib, ffmpeg-python, pandas.

Example Applications

Biomechanics labs: introduce gait cycle phases with visual and quantitative feedback.

Rehabilitation science: demonstrate abnormal gait patterns (if collected from patients).

Computer science courses: apply pose estimation to a real-world human movement task.

Sport performance: explore joint angles and timing during athletic movement.

Limitations

YOLOv8 Pose (trained on COCO) does not include toe/heel landmarks; foot events are approximated using ankle motion.

More precise foot kinematics could be achieved by integrating MediaPipe Pose or retraining a custom model with annotated foot landmarks.

Accuracy depends on video quality: side-view, stable camera, clear lighting, and minimal occlusion yield best results.

Learning Outcomes for Students

By the end of working through this project, you should be able to:

Describe how deep learning models can be applied to human motion analysis.

Implement a computer vision pipeline that processes video input into biomechanical outputs.

Interpret gait cycle events from kinematic data.

Critically evaluate the limitations of open-source pose estimation for biomechanics.

Would you like me to also include a step-by-step "How to Run in Colab" section (upload video → run setup → process → visualize) so students can follow it as a lab assignment?

You said:
yes- please include a how to run in colab section
ChatGPT said:

Perfect — here’s the updated README.md with a clear, step-by-step “How to Run in Colab” section added for your students.

README: Human Gait Analysis with YOLO Pose
Overview

This project demonstrates how to use computer vision and deep learning-based pose estimation to analyze human gait from video recordings. By combining an iPhone-recorded walking video with a YOLO pose detection model, we extract lower-body joint positions and compute biomechanical and spatiotemporal gait metrics.

This workflow is designed for undergraduate students in kinesiology, biomechanics, or computer science who are interested in applying computer vision to real-world human movement analysis.

Objectives

The code aims to:

Normalize video input (iPhone .MOV → .mp4) so it can be processed consistently in Google Colab.

Detect human pose keypoints using YOLOv8 Pose (hip, knee, ankle, etc.).

Compute biomechanical features:

Hip, knee, and ankle joint angles.

Smoothed time-series of joint motion.

Identify gait cycle events:

Heel strike (HS)

Toe strike (TS)

Heel off (HO)

Toe off (TO)

Quantify gait metrics:

Walking cadence (steps per minute).

Average durations of stance, swing, loading response, and push-off phases.

Visualize and export data:

Save annotated plots of joint angles and gait events.

Write CSV files of joint kinematics, key events, and raw keypoints.

Create an annotated video overlaying the skeleton and event labels.

Why This Matters

Gait analysis is a central topic in biomechanics, rehabilitation science, and sports performance. Traditional gait labs rely on expensive motion capture systems; here we demonstrate a low-cost, computer-vision-based approach using widely available tools (a smartphone camera and open-source models).

Students gain exposure to:

Practical use of deep learning for pose estimation.

Translating raw pose keypoints into biomechanically meaningful variables.

Signal processing techniques (smoothing, peak detection).

The connection between movement science and machine learning.

How to Run in Colab

Open Google Colab

Go to https://colab.research.google.com
.

Upload the provided notebook or paste the code into a new notebook.

Set up dependencies

Run the first cell to install required Python packages:

!pip -q install ultralytics opencv-python scipy numpy matplotlib tqdm ffmpeg-python pandas


Upload a video

Run the “Upload video” cell:

from google.colab import files
uploaded = files.upload()


Select an iPhone .MOV or .mp4 file of a person walking (side-view is best).

Normalize the video

The script converts your .MOV to a standard .mp4 (H.264, 30 fps).

Check the printout: it should confirm Normalized video: yourvideo_norm30.mp4.

Run YOLO pose estimation

Execute the main inference cell.

This will extract joint keypoints for hips, knees, and ankles frame by frame.

Compute gait metrics

The code calculates joint angles, cadence, and average gait phase durations.

Results are printed and saved into CSV files.

Visualize results

Run the plotting cells to see:

Knee angle traces with event markers.

Ankle trajectories with heel strike, toe off, etc.

Export results

CSV files (angles, events, raw keypoints) appear in the Colab file browser.

An annotated MP4 video with skeleton and labels is also saved.

Download files by right-clicking and selecting Download.

Example Applications

Biomechanics labs: introduce gait cycle phases with visual and quantitative feedback.

Rehabilitation science: demonstrate abnormal gait patterns (if collected from patients).

Computer science courses: apply pose estimation to a real-world human movement task.

Sport performance: explore joint angles and timing during athletic movement.

Limitations

YOLOv8 Pose (trained on COCO) does not include toe/heel landmarks; foot events are approximated using ankle motion.

More precise foot kinematics could be achieved by integrating MediaPipe Pose or retraining a custom model with annotated foot landmarks.

Accuracy depends on video quality: side-view, stable camera, clear lighting, and minimal occlusion yield best results.