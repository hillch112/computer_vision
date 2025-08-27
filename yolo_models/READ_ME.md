````markdown
# Squat Joint Angle Analyzer (YOLOv8 + OpenCV)

This project uses YOLOv8 pose estimation and OpenCV to analyze videos of squats and measure knee and hip angles frame-by-frame. It is designed specifically for **Google Colab** and outputs an annotated video showing joint angles in real-time, along with min/max angle summaries on the final frame.

---

## Overview

This script:
- Detects human pose landmarks using the `ultralytics/yolov8n-pose` model
- Identifies the left shoulder, hip, knee, and ankle
- Calculates:
  - **Knee angle** (hip → knee → ankle)
  - **Hip angle** (shoulder → hip → knee)
- Overlays:
  - Joint lines and keypoints
  - Real-time angle labels on each frame
- Outputs an annotated `.mp4` video that includes:
  - **Live joint angle measurements**
  - **Summary on the final frame**:
    - Minimum and maximum angles for both the hip and knee

---

## Requirements

- Python ≥ 3.8
- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- OpenCV

Install dependencies:

```bash
pip install ultralytics opencv-python
````

---

## File Setup (Google Colab Instructions)

1. **Upload a squat video to Colab**
   The script assumes the filename is:

   ```
   input_squat_video.mp4
   ```

   You can upload with:

   ```python
   from google.colab import files
   uploaded = files.upload()
   ```

2. **File Format Note**

   * The video **must be in `.mp4` format**.
   * `.mov` files (e.g., iPhone recordings) should be converted beforehand using:

     * HandBrake
     * QuickTime (`Export As...`)
     * `ffmpeg`:

     ```bash
     ffmpeg -i input.mov -vcodec libx264 -crf 23 output.mp4
     ```

3. **Verify File Readability**
   Use the following snippet to verify OpenCV can read the file:

   ```python
   import cv2
   cap = cv2.VideoCapture("input_squat_video.mp4")
   if not cap.isOpened():
       print("Failed to open video.")
   ```

---

## Output

After processing, a file named:

```
output_annotated_squat.mp4
```

will be created with:

* Joint angle overlays on each frame
* Min/max hip and knee angles shown on the final frame

---

## Example Use Case

* Record video of a subject performing squats
* Ensure full visibility of the left side (shoulder, hip, knee, ankle)
* Run the script in Colab with the video uploaded
* Receive an annotated video with biomechanical feedback

---

## Known Limitations

* Only tracks **left-side joints**
* Designed for **side-view squat analysis**
* May perform inconsistently if keypoints are occluded or missing
* No rep counting or right-side analysis (yet)

---

## Future Improvements

* Add support for multiple reps (automatic rep detection)
* Plot joint angles over time
* Export data to CSV for biomechanical analysis
* Add error/warning overlays (e.g., squat depth too shallow)

---

## License

This code is provided for educational and research purposes. No warranty is expressed or implied.

```

---

Let me know if you’d like:
- A version with screenshots or video output stills
- A student-facing `README` for a biomechanics lab context
- A version that includes markdown badges (e.g., Python version, Colab link)
```

