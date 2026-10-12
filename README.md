# FFT_Domain_CNN

## Overview

This repository contains the source code and testbench files for the proposed fully spectral Fast Fourier Transform (FFT)-domain Convolutional Neural Network (CNN) hardware architectures, developed using the Xilinx Vitis High-Level Synthesis (HLS) toolchain.

Two spectral CNN (SpCNN) architectures are provided, targeting the **ASCII character recognition** and **MNIST handwritten digit classification** datasets. The corresponding implementations are organized into the `ASCII` and `MNIST` directories, respectively.

## Repository Structure

Both dataset directories follow the same file organization.

### 1. Source Files

The `source_files` directory contains the HLS implementation and model parameters.

- **`Inference.cpp`** — Main implementation file containing the end-to-end inference pipeline, including FFT, convolution (CONV), activation functions (AF), pooling (POOL), and fully connected (FC) layers.
- **`Inference.h`** — Supporting header file defining required libraries, model hyperparameters, module declarations, SpCNN configurations, and fixed-point bit-width specifications.
- **`weights.h`** — Header file containing the trained model weights exported for each network layer.

### 2. Testbench Files

The testbench directory contains the simulation driver and test inputs used to validate the inference implementation.

- **`tb.cpp`** — Testbench source file used to execute and validate the end-to-end inference pipeline.
- **`Images/`** — Directory containing test images converted into C/C++ header files for HLS simulation. The images are organized into subdirectories corresponding to their respective class labels.

## Directory Organization

```text
FFT_Domain_CNN/
├── ASCII/
│   ├── Source_files/
│   │   ├── Inference.cpp
│   │   ├── Inference.h
│   │   └── Weights.h
│   ├── Testbench_files/
│   │   ├── tb.cpp
|   └── ├── Images/
│           ├── <class_0>/
│           ├── <class_1>/
│           └── ...
└── MNIST/
    ├── source_files/
    │   ├── Inference.cpp
    │   ├── Inference.h
    │   └── Weights.h
    ├── Testbench_files/
    │   ├── tb.cpp
    └── ├── Images/
            ├── <class_0>/
            ├── <class_1>/
            └── ...
```

*Note: The directory structure above illustrates the logical organization; actual paths may vary slightly.*

## Implementation and Validation

The source files are intended for use within a Xilinx Vitis HLS workspace. The testbench provides the inputs required to simulate and validate the end-to-end SpCNN inference functionality for both datasets.

