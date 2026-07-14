# Image Processing Final Project (2026)

## Phase 1: Frequency Domain (50 Points)
- [ ] **1.1 Vectorized 2D-DFT Implementation**
  - [ ] Matrix-based implementation ($W_M \cdot x \cdot W_N$) without loops.
  - [ ] Performance benchmarking (Time & 3D Plots vs. `fft2`).
- [ ] **1.2 Image Restoration (Deconvolution)**
  - [ ] Point Spread Function (PSF) extraction from `lonestar.tif`.
  - [ ] Inverse/Wiener filtering on `hubble_blurred.mat`.
  - [ ] Restoration and analysis of `iran_blurred.mat`.

## Phase 2: License Plate OCR (50 Points)
- [ ] **2.1 Preprocessing & Binarization**: Otsu thresholding & morphological noise cleaning.
- [ ] **2.2 Segmentation**: 8-Connected components & geometric filtering (Aspect ratio, Area).
- [ ] **2.3 Spatial Sorting**: Left-to-Right ordering based on Bounding Box $X_{min}$.
- [ ] **2.4 Classification**: Template matching (NCC) for 7-digit recognition.

## Phase 3: Bonus - License Plate Segmentation (30 Points)
- [ ] **3.1 Color-Based Method**: HSV mask + horizontal morphological closing.
- [ ] **3.2 Grayscale-Based Method**: Sobel vertical edges + density morphological integration.
- [ ] **3.3 Orientation Correction**: Oriented Bounding Box deskewing and 1000px width normalization.
