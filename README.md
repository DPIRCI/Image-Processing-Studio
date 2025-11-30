<style>
body {
    font-size: 10px;
}
</style>

# Digital Image Processing Studio — README

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

Add your own UI image here:

```
![UI Map](ui_map.png)
```

### **A — Control Panel**
Contains essential application controls such as **Open**, **Save**, **Reset**, and **Undo**.

### **B — Operations Panel**
Displays available operations under the selected category and provides parameter input fields for each operation.

### **C — Image Display Area**
Shows the **Original Image** and **Processed Image** side by side.  
The processed image updates immediately after each applied transformation.

### **D — Histogram Panel**
Displays grayscale and Matplotlib histograms.  
Supports histogram visualization before and after processing.

### **E — Categories Sidebar**
Navigation menu organizing algorithms into logical categories: **Basics**, **Intensity**, **Spatial Filters**, **Histogram**, and **Morphology**.

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
- Processing very high-resolution images (e.g., 4000×4000 px or larger)  
  may cause latency or increased memory usage.
- Large spatial filters (e.g., Gaussian 9×9, Median 7×7) can temporarily freeze the UI.

### **Real-Time Update Lag**
- Some operations—especially median filtering and large-kernel convolutions—may introduce momentary delays before updating the processed image.

### **Affine Transform Responsiveness**
- Continuous updates during shear or custom-angle rotation may cause short UI freezes due to intensive pixel interpolation computations.

### **Design Constraints**
- Some filters (e.g., median) internally convert the input to grayscale for stability and performance.
- This is an intentional optimization, not a limitation.

---

