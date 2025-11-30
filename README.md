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
![Figure 1: Application UI Map](Ekran görüntüsü 2025-11-30 172352.png)
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

## References

*(List your references here.)*
