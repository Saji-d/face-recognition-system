<div align="center">
  <img src="assets/banner.svg" alt="face-recognition-system banner" width="100%">
  <p><code>Classical face recognition notebook: Haar cascade detection and an LBPH recognizer trained per identity</code></p>

  ![Status](https://img.shields.io/badge/status-academic-22d3ee?style=flat-square&labelColor=0B0E1A)
  ![Type](https://img.shields.io/badge/type-classical%20CV-8b7cf6?style=flat-square&labelColor=0B0E1A)
  ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=c084fc&labelColor=0B0E1A)
  ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=c084fc&labelColor=0B0E1A)
  ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=c084fc&labelColor=0B0E1A)
  ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=c084fc&labelColor=0B0E1A)

  <a href="#-overview">Overview</a> · <a href="#-highlights">Highlights</a> · <a href="#-preview">Preview</a> · <a href="#-architecture">Architecture</a> · <a href="#-tech-stack">Tech Stack</a> · <a href="#-getting-started">Getting Started</a> · <a href="#-author">Author</a>
</div>

<img src="assets/divider.svg" alt="" width="100%">

## ◈ Overview

A single notebook, `lbph_face_recognition.ipynb`, that trains an OpenCV Local Binary Patterns Histogram (LBPH) recognizer on a folder of face images and then runs it on a live webcam feed.

This is a **classical computer vision project, not deep learning**. There is no neural network: faces are found with a Haar cascade and identified by comparing local texture histograms. It is an academic exercise that shows what traditional methods can do.

**Privacy:** the face datasets used for training are personal and are not included in this repository. No face photos are shipped.

<img src="assets/divider.svg" alt="" width="100%">

## ◈ Highlights

<table>
<tr>
<td width="33%" valign="top"><b>Haar cascade detection</b><br>Finds faces in webcam frames with <code>haarcascade_frontalface_default</code>.</td>
<td width="33%" valign="top"><b>LBPH recognizer</b><br>OpenCV <code>LBPHFaceRecognizer</code> trained with one label per identity.</td>
<td width="33%" valign="top"><b>Light preprocessing</b><br>Grayscale, 200x200 resize and histogram equalization.</td>
</tr>
<tr>
<td valign="top"><b>Simple augmentation</b><br>Two small rotations and two brightness shifts per image.</td>
<td valign="top"><b>Unknown handling</b><br>Predictions with an LBPH distance of 80 or more are labelled Unknown.</td>
<td valign="top"><b>Live loop</b><br>Draws a box and the name on each frame. Press <code>q</code> to quit.</td>
</tr>
</table>

<img src="assets/divider.svg" alt="" width="100%">

## ◈ Preview

<div align="center">
  <img src="docs/preview.webp" alt="Preview cover for the face recognition project" width="80%">
</div>

<img src="assets/divider.svg" alt="" width="100%">

## ◈ Architecture

```mermaid
flowchart LR
    A[Folder of images<br/>one sub-folder per person] --> B[Grayscale, resize 200x200,<br/>equalize histogram]
    B --> C[Augment: rotate and brightness]
    C --> D[Train LBPH recognizer]
    E[Webcam frame] --> F[Haar cascade face detection]
    F --> G[Crop and resize face]
    D --> H{LBPH predict}
    G --> H
    H -->|distance below 80| I[Show name]
    H -->|otherwise| J[Show Unknown]
```

<img src="assets/divider.svg" alt="" width="100%">

## ◈ Tech Stack

| Layer | Technologies | Purpose |
|---|---|---|
| Language | Python | Notebook code |
| Vision | OpenCV (contrib build, for `cv2.face`) | Detection, LBPH training and prediction |
| Arrays | NumPy | Image and label arrays |
| Environment | Jupyter | Running the notebook |

<img src="assets/divider.svg" alt="" width="100%">

## ◈ Getting Started

```bash
git clone https://github.com/Saji-d/face-recognition-system.git
cd face-recognition-system
pip install jupyter numpy opencv-contrib-python
jupyter notebook lbph_face_recognition.ipynb
```

1. Create a dataset folder with one sub-folder per person containing that person's face images (use your own and get consent).
2. Edit `dataset_path` in the first cell. It currently holds a Windows path from the author's machine.
3. Run the cells to train, then run the webcam cell. A camera is required.

The notebook trains on the images as given without detecting faces first, so the training images should already be tightly cropped faces.

<img src="assets/divider.svg" alt="" width="100%">

## ◈ Roadmap

- [ ] Detect and crop faces during training as well as at inference
- [ ] Hold out a test set and report accuracy
- [ ] Move paths and thresholds into variables or arguments

Also part of the wider [computer-vision-and-pattern-recognition](https://github.com/Saji-d/computer-vision-and-pattern-recognition) collection.

<img src="assets/divider.svg" alt="" width="100%">

## ◈ Author

**Sajidur Rahman Sajid** - Full-Stack Developer and AI engineer from Dhaka.

[Portfolio](https://www.sajidur.me) · [LinkedIn](https://www.linkedin.com/in/sajidur-rahman-sajid/) · [GitHub](https://github.com/Saji-d) · [Email](mailto:sajidsajidurrahman99@gmail.com)

<sub>Academic project. No datasets included.</sub>
