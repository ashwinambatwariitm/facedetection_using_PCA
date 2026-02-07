# Face Detection using PCA (Eigenfaces) – Extended Yale Dataset

This repository contains a complete implementation of **face detection / face recognition using Principal Component Analysis (PCA)**, also known as the **Eigenfaces method**, evaluated on the **Extended Yale Face Dataset**.

The project explains PCA **step by step**, making it suitable for beginners, students, and anyone learning **unsupervised learning techniques** for image processing.

---

## Project Overview

Face images are high-dimensional data where each pixel represents a feature. PCA helps by:
- Reducing dimensionality
- Removing redundancy
- Extracting the most significant facial features

This project demonstrates how PCA can be applied to face images for:
- Feature extraction
- Dimensionality reduction
- Face reconstruction
- Face recognition

---

## Algorithm Used

- Principal Component Analysis (PCA)
- Eigenfaces method
- Euclidean distance for matching (Point for future implementation)

---

## Dataset

### Extended Yale Face Dataset B (https://www.kaggle.com/datasets/jensdhondt/extendedyaleb-cropped-full)

- Grayscale face images
- Multiple subjects
- Variations in:
  - Illumination
  - Facial expressions
  - Pose (limited)
- Image format: `.pgm`

### Sample Directory Structure
```
cropped/
├── yaleB01/
│ ├── yaleB01_P00A+000E+00.pgm
│ ├── yaleB01_P00A+005E+10.pgm
│ └── ...
├── yaleB02/
└── ...
```

---

## Tech Stack

- Python 3.x
- NumPy
- Matplotlib
- Pillow (PIL)
- Scikit-learn
- Google Colab

---

## Workflow Explanation

### 1. Image Loading
- Load `.pgm` images from dataset folders
- flatten each image

### 2. Data Matrix Creation
- Each image becomes a row vector
- Shape:  
(number_of_images, height × width)


### 3. Mean Face Computation
- Compute average face across dataset
- Subtract mean face from each image to normalize data

### 4. PCA Computation
- Compute covariance matrix
- Extract eigenvalues and eigenvectors
- Sort eigenvectors by descending eigenvalues

### 5. Eigenfaces Generation
- Top `K` eigenvectors form Eigenfaces
- Each Eigenface represents a major facial feature

### 6. Projection into Eigenface Space
- Project original faces into reduced-dimensional space
- Compact representation of faces

### 7. Face Recognition (future task)
- Compare projected test face with training faces
- Use Euclidean distance to find closest match

---

## Visualizations

- Mean face
- Top Eigenfaces
- Original vs reconstructed faces
- Effect of number of PCA components

---

## How to Run

### Google Colab
1. Upload notebook to Colab
2. Mount Google Drive
3. Set dataset path
4. Run cells sequentially

## Learning Outcomes
- Understand PCA mathematically and practically
- Learn Eigenfaces-based face recognition
- Apply unsupervised learning to images
- Visualize dimensionality reduction effects
- Build a complete face recognition pipeline

## Future Enhancements
- Add SVM / kNN classifier on PCA features
- Compare PCA with LDA (Fisherfaces)
- Add accuracy metrics and confusion matrix
- Implement Incremental PCA
- Extend to real-time face recognition

## References
- Turk, M., & Pentland, A. (1991). Eigenfaces for recognition

## Citation

### Original Extended Yale Face Database B

```bibtex
@article{GeorghiadesKC01,
  author  = {A. S. Georghiades and P. N. Belhumeur and D. J. Kriegman},
  title   = {From Few to Many: Illumination Cone Models for Face Recognition under Variable Lighting and Pose},
  journal = {IEEE Transactions on Pattern Analysis and Machine Intelligence},
  year    = {2001},
  volume  = {23},
  number  = {6},
  pages   = {643--660}
}
