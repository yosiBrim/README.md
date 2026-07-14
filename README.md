# Advanced Image Processing: End-to-End Analysis, Recognition & Segmentation
**Jerusalem College of Technology -- Final Semester Project (2026)**

This repository contains the complete algorithmic implementation, benchmarking, and formal academic report for the Advanced Image Processing course. The project is structured into three rigorous engineering modules: Frequency Domain Signal Processing, Optical Character Recognition (OCR), and Computer Vision Segmentation.

---

## 📊 Project Progress Tracker & Checklist

### Part 1: Frequency Domain Processing & Deconvolution (50 Points)
- [ ] **1.1 Vectorized 2D-DFT Formulation & Benchmarking**
  - [ ] Mathematical Proof: Separability of 2D-DFT into Outer Product Matrix Multiplication ($W_M \cdot x \cdot W_N$).
  - [ ] Algorithmic Implementation: Vectorized DFT engine without iterative spatial/frequency loops.
  - [ ] Benchmark 1: 1D Uniform Averaging Array ($m=5$ and $m=200$, padded to $L=300$).
  - [ ] Benchmark 2: $2 \times 3$ Uniform Averaging Filter (padded to $200 \times 300$).
  - [ ] Benchmark 3: Sobel Edge Filter (padded to $200 \times 300$) vs. Analytical Frequency Response.
  - [ ] Benchmark 4: Checkerboard Image (`Fig0316(a)`) 3D Frequency Analysis.
  - [ ] Performance Comparison: Execution time and 3D surface plot analysis against MATLAB's `fft2`.
- [ ] **1.2 Optical Restoration via Inverse & Wiener Filtering**
  - [ ] PSF Extraction: Derivation of the optical Point Spread Function from `lonestar.tif` (Dirac impulse).
  - [ ] Celestial Restoration: Deconvolution and noise-controlled restoration of `hubble_blurred.mat`.
  - [ ] Terrestrial Intelligence Reconnaissance: Deblurring and target identification in `iran_blurred.mat` (without padding).
  - [ ] Synthesis & Conclusions: Analysis of frequency domain noise amplification and regularized filtering limits.

### Part 2: Automated License Plate Recognition (OCR Pipeline) (50 Points)
- [ ] **2.1 Preprocessing & Binarization**
  - [ ] Implementation of adaptive/global binarization (Otsu's thresholding methodology).
  - [ ] Morphological noise suppression (Opening/Closing kernels for salt-and-pepper and gap closure).
- [ ] **2.2 Morphological Segmentation & Geometric Filtering**
  - [ ] 8-Connectivity labeling and Bounding Box extraction ($[x_{\min}, y_{\min}, \text{width}, \text{height}]$).
  - [ ] Geometric Rejection Filtering: Empirical boundary thresholds for Aspect Ratio ($\frac{W}{H}$) and Area metrics.
- [ ] **2.3 Spatial Ordering Engine**
  - [ ] Left-to-Right 1D spatial sorting algorithm based on Bounding Box $X_{\min}$ coordinates.
- [ ] **2.4 Classification & String Generation**
  - [ ] Normalized Cross-Correlation (NCC) / Template Matching engine against canonical 0--9 digit templates.
  - [ ] System Validation: Testing on 14 digits across standard and degraded test plates (`LP_STANDARD`).
  - [ ] Performance Analysis & Error Budget: Documenting classification accuracy and edge-case failure modes.

### Part 3: Bonus -- Multi-Modal License Plate Segmentation (30 Points)
- [ ] **3.1 Method A: Color-Space Segmentation (HSV)**
  - [ ] RGB to HSV color-space transformation and chrominance isolation.
  - [ ] Yellow plate chrominance masking ($H \in [30^\circ, 50^\circ]$, high $S$) and horizontal morphological closing.
- [ ] **3.2 Method B: Grayscale Spatial-Frequency Segmentation**
  - [ ] High-frequency vertical edge detection using horizontal derivative operators (Sobel $\frac{\partial}{\partial x}$).
  - [ ] Morphological density integration: Connecting adjacent edge clusters into a unified plate bounding box.
- [ ] **3.3 Geometrical Normalization & Deskewing**
  - [ ] Orientation angle extraction ($\theta$) via Oriented Bounding Box / Principal Axis analysis.
  - [ ] Affine rotation correction (Deskewing via bicubic interpolation) and strict width normalization to $1000\text{px}$.
  - [ ] Final Evaluation: Robustness testing across 6 test images (color, grayscale, standard, and skewed orientations).

---

## 🛠️ Repository Architecture
* `/src/part1_freq/` -- Vectorized DFT implementation, benchmark test scripts, and deconvolution routines.
* `/src/part2_ocr/` -- Preprocessing, connected components labeling, spatial sorting, and template matching.
* `/src/part3_seg/` -- HSV color segmentation, Sobel edge segmentation, and affine deskewing modules.
* `/data/` -- Test images (`lonestar.tif`, `hubble_blurred.mat`, `iran_blurred.mat`, `LP_STANDARD`, etc.).
* `/report/` -- Complete academic LaTeX source files, TikZ diagrams, generated 3D surface plots, and final PDF report.
