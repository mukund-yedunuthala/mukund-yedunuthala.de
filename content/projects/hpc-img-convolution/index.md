+++
title = "Image convolution using Message Passing Interface (MPI)"
description = "Application of convolution kernels such as sharpening, blurring, edge detection to grayscale images in parallel using MPI."
date = 2023-03-15
updated = 2026-04-06
weight = 2
author = "Mukund Yedunuthala"
[taxonomies]
tags = ["C++", "High-Performance Computing", "Academia"]

[extra]
local_image = "projects/hpc-img-convolution/img/proj_mpi_tn.png"
show_remote_changes = true
social_media_card = "img/social_cards/projects_hpc_img_convolution.jpg"
katex = true
+++

## Overview

The core idea is to demonstrate parallel processing and perform a scalability study of an algorithm using MPI standard on university's high-performance computing cluster. Application of convolution kernels to grayscale images had been chosen as the algorithm in focus. Three convolution operations were implemented in C++ to be applied on varying sizes of images, namely:
- Blurring,
- Sharpening, and
- Edge detection. 

This project was a part of the course module "Introduction to High-Performance Computing and Optimization" in TU Bergakademie Freiberg. The project was expected to be delivered within 4 weeks, and without any assistance from fellow peers, or productivity enhancement tools.

## The problem

This programming project deals with the convolution of a grayscale image with kernels used for blurring, sharpening, and edge detection. The program, built using C++ and MPI, has to demonstrate strong scalability on the parallel computing cluster. 

Grayscale images used in this project have one channel with 8-bit depth. They should use uncompressed PGM data format which should be parsed by the C++ program. The following convolution kernels are applied to manipulate the images, namely (a) Gaussian blur, (b) Sharpen, and (c) Edge detection:
$$\frac{1}{16}
    \begin{bmatrix}
        1 & 2 & 1\\\\ 
        2 & 4 & 2\\\\ 
        1 & 2 & 1
    \end{bmatrix},\ 
    \begin{bmatrix}
        0 & -1 & 0 \\\\ -1 & 5 & -1 \\\\ 0 & -1 & 0
    \end{bmatrix},\ 
    \begin{bmatrix}
        0 & -1 & 0 \\\\ -1 & 5 & -1 \\\\ 0 & -1 & 0
    \end{bmatrix}
$$

The respective convolution kernel is used to obtain a new pixel value $I^∗ (x, y)$ at position $(x, y)$ in the image from the old pixel value $I(x, y)$ and its surrounding pixel values such that
$$ 
I^*(x,y) = \sum_{i=1}^{n}\sum_{i=1}^{n}I(x-i+2,y-j+2)k(i,j) 
$$
where k is a 3 × 3 convolution kernel.

### Pain points

Since it depends on the neighbouring values, the parallel implementation must account for edges of the image as well as that of the chunks that were divided upon provision of multiple cores. This is handled using a combination of exchanging halo information and padding. 

![Halo Information](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution/-/raw/main/inputs/MPI.png)
Fig. 1: Distribution of the image data between processes P0 . . . P3 . The dashed lines
mark the halo rows that need to be communicated between neighbouring processes.

## Solution

The built solution uses CMake build system. From the [documentation](https://mukundyedunuthala.page/docs/hpc-img-convolution/api/main), the executable:

> Reads a given input PGM file and performs convolution using given kernels and writes output to indicated file. Outputs 1 file, one for each convolution kernel. Defaults indicate that blur is performed 5 times, whereas the other two are limited to 1. Supports parallel processing using MPI. Input array is divided into chunks if more than 1 process exist in the swarm. File and terminal outputs occur on root process.

### Build

Assuming one is located at the root of the project, the following snippet details instructions to build the executable.

```bash
mkdir build && cd build
cmake ..
make
```

It offers a couple of checks and options that aim to provide flexibility. E.g.

```bash
mkdir build && cd build
cmake -DWITH_MPI=False ..
make
```

This builds the executable that is entirely serialized. Might be more suitable for
GNU compiler. The default is ``WITH_MPI=True``.

```bash
mkdir build && cd build
cmake -DWITH_DOXYGEN=True ..
make docs
```

This generates the doxyfile that could be used to generate documentation with make. The default is ``WITH_DOXYGEN=False``. This however generates the documentation using default theme provided by Doxygen.

### Usage

Once the executable is built, the sequential version’s execution is straightforward, provided that the current working directory is ``build`` as explained earlier.

```bash
./HPC2020
```

In case of the MPI version, the execution is recommended to be through ``mpirun`` or ``mpiexec``.

```bash
mpirun -np 2 ./HPC2020
```

The input file name is, at the moment, supposed to be changed through ``main.cpp`` file only and the file must be present in ``inputs`` directory. The generated image can be found in ``output`` directory.

## Results
The following images show the original image with 512 x 512 pixels size, as well as the results upon application of edge detection, gaussian blur, and sharpening.

|  |  |
| :---: | :---: |
| ![Original image](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution/-/raw/main/inputs/512.png?ref_type=heads) | ![Blurred image](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution/-/raw/main/output/512blur.png?ref_type=heads) |
| **Fig. 2: Original** | **Fig. 3: Blurred** |
| | |
| ![Edges detected](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution/-/raw/main/output/512edge.png?ref_type=heads) | ![Sharpened image](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution/-/raw/main/output/512sharpen.png?ref_type=heads) |
| **Fig. 4: Edges** | **Fig. 5: Sharpened** |

## Links

- Git repository: [GitLab](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution)
- Documentation: [Full documentation](https://mukundyedunuthala.page/docs/hpc-img-convolution/)
