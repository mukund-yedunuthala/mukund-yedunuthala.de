+++
title = "Image convolution using Message Passing Interface (MPI)"
description = "Application of convolution kernels such as sharpening, blurring, edge detection to grayscale images in parallel using MPI."
date = 2023-03-15
weight = 2

[taxonomies]
tags = ["C++", "High-Performance Computing", "Academia"]

[extra]
local_image = "img/proj_mpi_tn.png"
+++
#### Repository: [git/hpc-img-convolution](https://git.mukund-yedunuthala.de/mukund-yedunuthala/hpc-img-convolution)
#### Documentation: [https://mukund-yedunuthala.gitlab.io/hpc-img-convolution/](https://mukund-yedunuthala.gitlab.io/hpc-img-convolution/)

Introduction
============

This is a C++ project that applies convolution kernels to greyscale images
using Message Passing Interface (MPI) to perform that in parallel. It is 
part of a course called *High performance computing and optimization* at 
TU Bergakademie Freiberg. This serves as a capstone project in an introductory
course to parallel processing. 

Build
=====

This project utilizes CMake build system. Assuming one is located at the root
of the project, the following snippet details instructions to build the 
executable.

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

This generates the doxyfile that could be used to generate documentation with ``make``.
The default is ``WITH_DOXYGEN=False``. WIP.