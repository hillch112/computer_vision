# Computer Vision Tools for Human Movement Analysis

This repository is dedicated to developing **computer vision–based tools** for analyzing **human movement**, with a special focus on applications in **biomechanics education**. It provides example scripts, tutorials, and real-time demonstrations using pose estimation models to extract joint data and calculate biomechanical variables such as joint angles, ranges of motion, and repetition patterns.

---

## 🧠 Purpose

The primary goal of this project is to support **undergraduate biomechanics instruction** through interactive, computer vision–driven analysis of human movement. Whether it’s analyzing squats, bicep curls, gait patterns, or other fundamental motor actions, this repo provides open tools and models to:

- Teach biomechanics concepts using real-world videos
- Automate joint angle and posture analysis
- Generate visualizations to support student learning
- Encourage data literacy and programming skills in kinesiology

---

## 🛠️ Features

- ✅ YOLOv8 Pose and MediaPipe Holistic-based examples
- ✅ Joint angle calculation and overlay on videos
- ✅ Frame-by-frame tracking of movement patterns
- ✅ Min/max angle summaries and time-series analysis
- ✅ Output in annotated video or structured CSV format
- ✅ Ready to run in **Google Colab** (ideal for classroom use)

---

## 📂 Repository Structure

Each file or folder in the repository corresponds to a specific use case or model:

| File/Folder                        | Description |
|-----------------------------------|-------------|
| `squat_yolov8_pose.py`            | Annotated squat angle analyzer using YOLOv8 |
| `bicep_curl_holistic.py`          | Shoulder-elbow-wrist tracking with MediaPipe |
| `README.md`                       | Main project overview |
| `examples/`                       | Example videos, screenshots, and outputs |
| `utils/`                          | Utility functions for visualization, data export, etc. |
| `lab_assignments/`                | Companion materials for student labs (in progress) |

---

## 🔍 Use in the Classroom

This repo is ideal for:
- Biomechanics and kinesiology lab assignments
- Introductory computer vision in human movement science
- STEM teaching modules that integrate coding and applied physiology
- Demonstrating real-time pose tracking and feedback systems

Students can record their own movement with a smartphone, upload it to Google Colab, and receive visual and numerical feedback in minutes.

---

## 💡 How to Get Started

1. Clone or fork this repository
2. Open a provided `.ipynb` file in [Google Colab](https://colab.research.google.com/)
3. Upload your `.mp4` video or mount your Google Drive
4. Run the script and download the annotated results

**Note:** All video files must be in `.mp4` format. `.mov` or other formats should be converted prior to upload. Many of the code examples have this conversion already included.

---

## 🤝 Contributing

Contributions are welcome!

We encourage educators, students, developers, and biomechanics researchers to:
- Submit new analysis examples
- Add support for new model types (e.g., OpenPose, BlazePose)
- Improve visualization tools and performance
- Propose new biomechanics applications (e.g., gait, jump analysis)

To contribute:
1. Fork the repository
2. Create a new branch
3. Submit a pull request with a clear description

---

## 📄 License

This project is licensed under the MIT License. See `LICENSE` for details.

---

## 📫 Contact

For questions, collaborations, or classroom integration inquiries, please reach out via GitHub Issues or submit a discussion topic in the Community tab.

