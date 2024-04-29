+++
title = "Image convolution using Message Passing Interface (MPI)"
description = "Anwendung von Faltungskernen wie Schärfung, Unschärfe und Kantenerkennung auf Graustufenbilder mittels MPI zur parallelen Verarbeitung."
date = 2023-03-15
weight = 2

[taxonomies]
tags = ["C++", "High-Performance Computing", "Academia"]

[extra]
local_image = "img/proj_mpi_tn.png"
+++
#### Git-Repository: [git/hpc-img-convolution](https://git.mukund-yedunuthala.de/mukund-yedunuthala/hpc-img-convolution)
#### Dokumentation: [https://docs.mukund-yedunuthala.de/hpc-img-convolution/](https://docs.mukund-yedunuthala.de/hpc-img-convolution/)

Anleitung
=========

This is a C++ project that performs convolution operations such as blurring, sharpening, or edge detection to greyscale images and utilize Message Passing Interface (MPI) to perform that in parallel.A C++ project that performs convolution operations such as blurring, sharpening, or edge detection to greyscale images and utilize Message Passing Interface (MPI) to perform that in parallel.

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

This generates the doxyfile that could be used to generate documentation with make. The default is ``WITH_DOXYGEN=False``. This however generates the documentation using default theme provided by Doxygen. To get themed documentation as presented here, the working directory should be ``docs`` where a separate ``Makefile`` is provided which integrates ``Sphinx``.

Usage
=====
Once the executable is built, the sequential version’s execution is straightforward, provided that the current working directory is ``build`` as explained earlier.

```bash
./HPC2020
```

In case of the MPI version, the execution is recommended to be through ``mpirun`` or ``mpiexec``.

```bash
mpirun -np 2 ./HPC2020
```

The input file name is, at the moment, supposed to be changed through ``main.cpp`` file only and the file must be present in ``inputs`` directory. The generated image can be found in ``output`` directory.

Showcase
========
The following images show the original image with 512 x 512 pixels size, as well as the results upon application of edge detection, gaussian blur, and all three convolutions applied simultaneously.

| ![Original image](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution/-/raw/main/inputs/512.png?ref_type=heads) |
|:--:|
|  Fig. 1: Original Image |


| ![Blurred image](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution/-/raw/main/output/512blur.png?ref_type=heads) |
|:--:|
|  Fig. 2: Blurred Image |


| ![Edges detected](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution/-/raw/main/output/512edge.png?ref_type=heads) |
|:--:|
|  Fig. 3: Edges detected |


| ![Sharpened image](https://gitlab.com/mukund-yedunuthala/hpc-img-convolution/-/raw/main/output/512sharpen.png?ref_type=heads) |
|:--:|
|  Fig. 4: Sharpened Image |