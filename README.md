# Image Processing Application README

**Student ID:** 24070001119

**Name:** Doğa Pirci

## Table of Contents

1. [Introduction / App Overview](#introduction)
2. [UI Map](#app-overview--ui-map)
    * 2.1. [Application Overview](#application-overview)
    * 2.2. [User Interface (UI) Map](#user-interface-ui-map)
3. [Implemented Features (Checklist)](#implemented-features-checklist)
4. [Short Notes on Key Parameters](#short-notes-on-key-parameters)
5. [Known Limitations](#known-limitations)

---
## 1. Introduction / App Overview
Digital Image Processing Studio is a desktop application developed as part of the COMP 4360 Image Processing midterm assignment.  
The goal of this tool is to provide an interactive, user-friendly environment for applying a variety of image processing algorithms in real time.

The application offers:
- Side-by-side visualization of the **Original Image** and **Processed Image**
- Real-time updates after each operation
- Parameter-controlled filters and transformations
- Undo history for safe experimentation
- Histogram analysis tools
- A complete set of fundamental and intermediate image processing operations

---

## 2. UI Map


![UI Map](ui_map.png)


### **A — Control Panel**
This panel, located beneath the title bar, houses the core file management and application state controls. It provides quick access to essential functions, including Open Image, Save Image, and interface controls such as Reset and Undo.

### **B — Operations Panel**
Serving as the dynamic control center, this panel lists the specific operations (e.g., Contrast Stretch, Negative, and Gamma) available under the category currently selected in the E panel. Crucially, this area also enables the user to adjust the parameters or set the value for the chosen operation, providing granular control over the processing intensity.

### **C — Image Display Area**
This critical section is dedicated to visualization and comparison. It simultaneously displays the Original Image and the Processed Image. A key feature is its real-time feedback: the Processed Image is dynamically updated immediately after every operation, allowing the user to instantly assess the visual outcome of the applied filter or transformation.

### **D — Histogram Panel**
Positioned at the bottom of the interface, this area provides analytical tools, specifically the Grayscale and Matplotlib histograms. These tools are essential for visualizing the numerical effects of the applied image processing operations on the image's pixel distribution.

### **E — Categories Sidebar**
This is the primary navigation menu on the left side of the application. It allows the user to select the desired algorithms and filters, organizing them into logical categories like Basics, Intensity, Histogram, and Morphological.

---

## 3. Implemented Features (Checklist)

### **I/O & Display**
- [x] Supports JPEG / PNG
- [x] Side-by-side original and processed images
- [x] Real-time update rendering

### **Core Application Controls**
- [x] Open Image
- [x] Save Processed Image
- [x] Reset to Original
- [x] Undo History System

### **Basic & Affine Transformations**
- [x] Grayscale Conversion
- [x] Horizontal / Vertical Flip
- [x] Rotate (90°, -90°, and custom angle)
- [x] Scale (Uniform, X-axis, Y-axis)
- [x] Translate (dx, dy)
- [x] Shear (X, Y, or both)

### **Intensity Transformations**
- [x] Contrast Stretching
- [x] Gamma Correction (0.1–5.0)
- [x] Negative Transformation

### **Spatial Filters**
- [x] Mean / Box Filter
- [x] Gaussian Filter
- [x] Median Filter
- [x] Sobel (X, Y, magnitude)
- [x] Laplacian

### **Histogram Operations**
- [x] Histogram Display
- [x] Histogram Equalization

### **Morphological Operations**
- [x] Global Thresholding
- [x] Otsu Thresholding
- [x] Erosion / Dilation
- [x] Opening / Closing

---

## 4. Short Notes on Key Parameters

### **Kernel Size (Spatial Filters)**
- Only **odd kernel sizes (3, 5, 7, …)** are supported.
- This ensures proper centering of the filter mask.
- Minimum valid size: **3×3**
- 1×1 (identity) and 2×2 (off-center) kernels are intentionally excluded.

### **Gamma Correction**
- Range: **0.1 – 5.0**
- γ < 1 → brightens the image  
- γ > 1 → darkens the image  

### **Structuring Element (Morphology)**
- User-defined kernel size controls the strength of erosion/dilation.
- Larger kernels → stronger morphological effects.

---

## 5. Known Limitations

### **Performance & Memory**
- Processing very high-resolution images (e.g., 4000×4000 px or larger) may cause latency or increased memory usage.  
- Large spatial filters (e.g., Gaussian 9×9, Median 7×7) can temporarily freeze the UI during computation.

### **Real-Time Update Lag**
Although the application is designed for real-time feedback, computationally heavy operations (such as large Gaussian or Median kernels, e.g., 15×15) may cause short UI freezes before the processed image updates.

### **Affine Transform Responsiveness**
Continuous updates during complex affine transformations (e.g., Shear or custom-angle Rotation) may lead to temporary UI unresponsiveness.  
This is due to the high computational cost of real-time pixel interpolation.

### **Design Constraints**
- Some operations (e.g., **median filtering**) internally convert the image to grayscale to ensure stable, optimal, and consistent intensity-based processing.
- This behavior is intentional and implemented for performance and algorithmic correctness.

### **Kernel Size Restriction**
Spatial filters require a minimum kernel size of **3×3**.  
1×1 kernels behave as identity operations, and 2×2 kernels lack a well-defined center, often leading to non-standard or unstable behavior.

### **Internal Grayscale Processing**
Certain filters rely on single-channel intensity calculations; therefore, they automatically process images in grayscale internally to maintain performance, stability, and consistent results.

### 6.References
[Colab Notebook](https://colab.research.google.com/drive/1eS4952_xnsUxy9tm0MpUv-QJKgmmn6v2?usp=sharing#scrollTo=bRgjfHweFTX9)

</div>

