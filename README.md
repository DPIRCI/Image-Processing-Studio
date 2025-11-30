# Image-Processing-Studio
## FACULTY OF ENGINEERING
### DEPARTMENT OF COMPUTER ENGINEERING

**COMP 4360 IMAGE PROCESSING**

# Image Processing Application README

**Student ID:** 24070001119

**Name:** Doğa Pirci

## Table of Contents

1. [Introduction](#introduction)
2. [App Overview & UI Map](#app-overview--ui-map)
    * 2.1. [Application Overview](#application-overview)
    * 2.2. [User Interface (UI) Map](#user-interface-ui-map)
3. [Implemented Features Summary](#implemented-features-summary)
    * 3.1. [Core Application Requirements](#core-application-requirements)
    * 3.2. [Minimum Feature Set Details](#minimum-feature-set-details)
4. [Appendices and Supplementary Material](#appendices-and-supplementary-material)
5. [References](#references)

---

## Introduction

This desktop application, **Digital Image Processing Studio**, was developed as part of the COMP 4360 Image Processing midterm assignment. The goal of the project is to provide an interactive, user-friendly environment where fundamental and advanced image processing operations can be applied in real time. The application integrates essential functions such as **affine transformations**, **intensity adjustments**, **spatial filtering**, **histogram analysis**, and **morphological operations** into a clean and intuitive interface.

The purpose of this tool is not only to demonstrate the implementation of core digital image processing algorithms but also to **visualize their effects immediately** through side-by-side comparisons of the original and processed images. Each operation is designed to be easily accessible, parameter-driven, and responsive, making the application suitable for both educational use and practical experimentation.

In addition, the application includes an **Undo history system**, allowing users to safely explore multiple transformations without losing previous states — a feature that significantly enhances usability.

---

## App Overview & UI Map

### 1. Application Overview

The **Digital Image Processing Studio** is a desktop application designed to provide users with a comprehensive set of fundamental and intermediate image processing operations. The application is built around an intuitive user interface that allows for the real-time application and visual assessment of various algorithms, ranging from basic manipulations (e.g., Grayscale conversion, Rotation) to complex spatial filtering and morphological operations.

A key feature of the application is the **real-time comparison** between the **Original Image** and the **Processed Image**, allowing immediate feedback on the impact of applied parameters. Furthermore, the integrated **Histogram Analysis** provides numerical insight into the pixel intensity distribution after processing.

### 2. User Interface (UI) Map
![Figure 1: Application UI Map](ui_map)
The main application window is structured into five primary functional areas, which are denoted by the labels **A** through **E** in Figure 1.



#### **A: Control Panel / Core Operations**

This panel, located beneath the title bar, houses the core file management and application state controls. It provides quick access to essential functions, including **Open Image**, **Save Image**, and interface controls such as **Reset** and **Undo**.

#### **B: Operations Panel**

Serving as the dynamic control center, this panel lists the specific operations (e.g., Contrast Stretch, Negative, and Gamma) available under the category currently selected in the **E** panel. Crucially, this area also enables the user to **adjust the parameters** or **set the value** for the chosen operation, providing granular control over the processing intensity.

#### **C: Viewing and Processing Area**

This critical section is dedicated to visualization and comparison. It simultaneously displays the **Original Image** and the **Processed Image**. A key feature is its **real-time feedback**: the Processed Image is dynamically updated immediately after every operation, allowing the user to instantly assess the visual outcome of the applied filter or transformation.

#### **D: Histogram Analysis**

Positioned at the bottom of the interface, this area provides analytical tools, specifically the **Grayscale** and **Matplotlib histograms**. These tools are essential for visualizing the numerical effects of the applied image processing operations on the image's pixel distribution.

#### **E: Processing Categories (Navigation Sidebar)**

This is the primary navigation menu on the left side of the application. It allows the user to select the desired algorithms and filters, organizing them into logical categories like **Basics**, **Intensity**, **Histogram**, and **Morphological**.

---

## Implemented Features Summary

This section confirms the successful implementation of all Minimum Feature Set requirements, providing real-time image processing functionality and analysis.

### Core Application Requirements

| Feature | Implemented | Notes |
| :--- | :---: | :--- |
| **I/O & Display** | $\checkmark$ | Supports standard image I/O (JPEG, PNG). Displays Original and Processed images side-by-side (UI Label C). |
| **Visualization** | $\checkmark$ | Processed Image updates dynamically and immediately after applying any filter/transformation. |
| **Build** | $\checkmark$ | Runs as a single compiled executable (.exe). |

### Minimum Feature Set Details

#### A. Basic & Affine Transforms (B)

| Feature | Implemented | Key Parameters / Notes |
| :--- | :---: | :--- |
| **Basics** | $\checkmark$ | Includes Grayscale conversion, Flip (H/V), 90° Rotations, and Reset to Original. |
| **Affine** | $\checkmark$ | Supports **Rotation** (angle), **Scale** (uniform/X/Y), **Translate** (dx, dy), and **Shear** (X, Y, both). |

#### C. Intensity Transformations

| Feature | Implemented | Key Parameters / Notes |
| :--- | :---: | :--- |
| **Key Transforms** | $\checkmark$ | Includes **Contrast Stretching** ($r_{\min}$, $r_{\max}$), **Gamma Correction** ($\gamma$ slider, e.g., 0.1 to 5.0), and **Negative** inversion. |

#### D. Spatial Filters

| Feature | Implemented | Key Parameters / Notes |
| :--- | :---: | :--- |
| **Linear & Non-Linear** | $\checkmark$ | Implements **Mean/Box**, **Gaussian**, and **Median** filters, all controlled by a user-defined **kernel size** (e.g., 3x3, 5x5). |
| **Edge Detection** | $\checkmark$ | Includes **Laplacian** (3x3) and **Sobel** (X/Y magnitude) filters. |

#### E. Histogram & F. Morphological Operations

| Feature | Implemented | Key Parameters / Notes |
| :--- | :---: | :--- |
| **Histogram** | $\checkmark$ | Displays the current image histogram and includes **Histogram Equalization** for contrast enhancement. |
| **Morphology** | $\checkmark$ | Supports **Global/Otsu Thresholding** (Binary), basic operations (**Erode**, **Dilate**), and compound operations (**Open**, **Close**). |
| **Kernel** | $\checkmark$ | Morphological operations utilize a user-definable **structuring element** size. |

---

## Appendices and Supplementary Material

*(This section is reserved for additional materials such as code snippets, extra diagrams, or detailed algorithm explanations.)*

---

# ⚠️ Known Limitations

This section outlines known functional and performance limitations of the Digital Image Processing Studio application, primarily due to implementation constraints and design choices made to prioritize core functionality.

## 1. Performance and Memory Constraints
* **Large Image Processing:** The application currently processes all images on the main thread and holds a significant undo history. Processing **high-resolution images (e.g., $>4000 \times 3000$ pixels)** may lead to noticeable **latency** or **out-of-memory** issues, especially when applying iterative spatial filters.
* **Real-time Update Lag:** While designed for real-time feedback, complex filters (like large Gaussian or Median kernels, e.g., $15 \times 15$) may cause temporary freezing of the UI during computation before the processed image (UI Label C) updates.

## 2. Feature Implementation Limitations
* **Kernel Size Restriction:** Spatial filters (Mean, Gaussian, Median) are currently restricted to use only **odd-numbered kernel sizes** (e.g., $3 \times 3$, $5 \times 5$, $7 \times 7$). Even-sized kernels were intentionally excluded to simplify **boundary handling** and **centering** of the filter mask over the pixel.
* **Default Kernel Start:** For performance testing consistency, all spatial filters (Section D) default to a minimum kernel size of $\mathbf{3 \times 3}$. Smaller $1 \times 1$ kernel operations are excluded as they represent the identity operation and offer no practical filtering value.
* **Color Space Management:** While supporting color image I/O, the application primarily performs filtering and analysis operations (Sections D & E) in the **RGB color space** by applying them to the Red, Green, and Blue channels independently. This channel-by-channel approach is computationally straightforward but is **not optimal** for tasks requiring accurate chromaticity and lightness processing. Consequently, the resulting color image may exhibit **perceptual color shifts** or **artifacts** compared to processing methodologies that separate intensity and chrominance, such as utilizing the **Luminance (L) channel** in the L*a*b* or HSV color spaces..

---

# ⚙️ Short Notes on Key Parameters

This section provides brief explanations and rationale for the chosen parameters in the implemented image processing functions.

| Operation / Feature | Key Parameter | Value Range & Rationale |
| :--- | :--- | :--- |
| **Spatial Filtering** (Mean, Gaussian, Median) | **Kernel Size ($N \times N$)** | **Range:** $3, 5, 7, \dots$ (Odd integers only). |
| | | **Note:** The size of the kernel directly dictates the **degree of smoothing** or **noise reduction**. A larger kernel size means greater averaging/median calculation over a larger neighborhood, resulting in more significant smoothing but also **greater blurring** of fine details and edges. The minimum $3 \times 3$ is chosen as the smallest neighborhood that provides meaningful filtering. |
| **Intensity Transformation** | **Gamma ($\gamma$)** | **Range:** Typically $0.1$ to $5.0$. |
| | | **Note:** Gamma Correction ($\mathbf{s = c \cdot r^\gamma}$) is used to non-linearly adjust image brightness and contrast. |
| | | * **$\gamma < 1.0$ (e.g., 0.5):** Increases overall brightness, enhancing details in **shadows** (dark areas). |
| | | * **$\gamma > 1.0$ (e.g., 2.0):** Decreases overall brightness, enhancing details in **highlights** (bright areas). |
| **Intensity Transformation** | **Contrast Stretch** ($r_{\min}$, $r_{\max}$) | **Range:** $0$ to $255$. |
| | | **Note:** This linear stretch maps the current pixel range ($\mathbf{[r_{\min}, r_{\max}]}$) to the full output range $[0, 255]$. The choice of $r_{\min}$ and $r_{\max}$ is critical: if set too close to the image's actual minimum/maximum intensity, it may **clip** (saturate) pixels, losing information. |
| **Edge Detection** | **Sobel Filter** | **Kernel:** $\mathbf{3 \times 3}$. |
| | | **Note:** Sobel uses two $3 \times 3$ kernels ($G_x$ and $G_y$) to approximate the image gradient in the horizontal and vertical directions. The $\mathbf{3 \times 3}$ size is standard because it provides a good balance between **noise suppression** and **edge localization** accuracy. Larger kernels (e.g., $5 \times 5$) would blur the image too much before detecting the edge, leading to thicker, less precise edges. |
| **Morphology** | **Structuring Element Size** | **Range:** User-definable odd size, usually $3 \times 3$ or $5 \times 5$. |
| | | **Note:** The size of the structuring element (kernel) determines the **extent of morphological effect**. Larger elements cause more severe erosion or dilation, which is useful for removing larger noise components (Erosion) or filling bigger holes/gaps (Dilation). |
---
## References

*(List your references here.)*
