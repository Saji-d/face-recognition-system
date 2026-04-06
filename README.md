# 🙂 Face Recognition using LBPH (OpenCV)

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Face Recognition](https://img.shields.io/badge/Face%20Recognition-4CAF50)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?logo=opencv&logoColor=white)

A classical computer vision project that implements face recognition using OpenCV’s Local Binary Patterns Histogram (LBPH) algorithm, emphasizing traditional feature-based recognition techniques.

---

## 📌 Overview

This project implements a **classical face recognition system** using the **Local Binary Patterns Histogram (LBPH)** algorithm provided by OpenCV.

The focus is on **feature-based face representation**, identity prediction, and robustness to lighting variations, highlighting traditional computer vision techniques as an alternative to deep learning–based approaches.

---

## 🎯 Objectives

- Detect faces from images using OpenCV  
- Extract facial features using **Local Binary Patterns (LBP)**  
- Train an LBPH-based face recognizer  
- Predict and recognize known faces from test images  

---

## 🧠 Algorithm Used: LBPH

**Local Binary Patterns Histogram (LBPH)** works by:
- Converting pixel neighborhoods into binary patterns  
- Encoding local texture information  
- Building histograms to represent facial features  
- Comparing histograms for face recognition  

Key advantages:
- Works well under varying lighting conditions  
- Simple and interpretable  
- Computationally efficient  

---

## 📂 Dataset

- Face images organized by individual identities  
- Images are preprocessed through:
  - Grayscale conversion  
  - Face detection  
  - Resizing and normalization  

Each identity is learned during training and later recognized during testing.

---

## ⚙️ Implementation Details

- **Language:** Python  
- **Library:** OpenCV  
- **Environment:** Jupyter Notebook  

Core components include:
- Face detection using OpenCV classifiers  
- Feature extraction using LBP  
- Classification using LBPH face recognizer  

---

## 📈 Results

- Successfully recognizes known faces from test images  
- Performs reliably under moderate lighting changes  
- Demonstrates effectiveness of classical vision methods  

---

## 🧪 Key Learnings

- Understanding texture-based feature extraction  
- Difference between classical and deep learning approaches  
- Role of preprocessing in face recognition accuracy  

---

## 📎 Note

This project is also part of a broader computer vision repository:  
https://github.com/Saji-d/computer-vision-and-pattern-recognition

---

## 👤 Author

**Sajidur Rahman Sajid**  
Computer Science & Engineering (CSE)  
Aspiring **AI / Machine Learning Engineer**
