+++
title = "Modeling of radiative heat-exchange using Finite Element Method (FEM)"
description = "A finite element method based solver for a mathematical model of heat-transfer comprised of a coupled system of conduction and radiation."
date = 2022-10-15
updated = 2026-04-07
weight = 3

[taxonomies]
tags = ["Python", "Academia"]

[extra]
local_image = "projects/radiative-ht-fem/img/Pasted image 20260407153658.png"
social_media_card = "img/social_cards/projects_radiative_ht_fem.jpg"
+++

A finite element method based solver for a mathematical model of heat-transfer comprised of a coupled system of conduction and radiation.

## Overview

The energy transfer between two metallic bodies could be characterized by three phenomena, namely conduction, convection and radiation. The primary cause for such heat transfer is a difference in the temperature of the bodies. The amount of heat transferred between the bodies depends additionally on their respective material's properties, characterized by concepts such as conductivity, emissivity etc. 

Conduction characterizes heat transferred through an exchange of energy between molecules in proximity without any movement of such subatomic particles. The medium of transfer thus influences the heat transfer directly. This is characterized by Fourier law of heat conduction. 
$$
\begin{equation}\label{eq:fl_cond}
            q_x = -kA\frac{\partial T}{\partial x}
        \end{equation}
$$

Thermal radiation, on the other hand, has been described as "a stream of electromagnetic radiation emitted by a material entity on account of its finite temperature." It is emitted from the surfaces of the bodies, and could either be absorbed or reflected on impacting another object. The difference between the amount of heat absorbed or reflected depends on external factors like the geometry or the orientation of these objects. The governing equation for this type of energy transfer is derived from the Stefan-Boltzmann Law which describes the maximum "flux" that can be emitted by radiation from a black surface. The quantity $\sigma$, known as Stefan-Boltzmann constant, has value $5.670367 \times 10^{-8} W m^{-2} K^{-4}$. Figure 1[^1] is a representative image of this phenomenon.
$$
\begin{equation}
	q = \sigma T_w^4
\end{equation}
$$

<div align="center">
  <img src="img/Pasted image 20260407151225.png" alt="Thermal radiation between two bodies at different temperatures." width="500">
  <p><em>Fig. 1: Thermal radiation between two bodies at different temperatures.</em></p>
</div>

### Motivation

Celestial bodies such as asteroids and airless bodies, such as the Moon, are covered with a loose, unconsolidated material termed as *regolith*. Owing to the lack of disturbing factors, the regolith preserves the characteristics of that body for a long time. The thermal properties of such materials could be evaluated using appropriate finite element mesh frameworks. An analysis of temperature distribution could output results that can push further analyses of other properties such as their thermal conductivities.

The primary mode of energy transfer to these particles is through electromagnetic radiation from the nearest heat sources, usually a star. The influence of such thermal radiation on these particles forms the motivation behind this programming project.

### Aims and objectives

The aim of this programming project is as follows: To study and model radiative heat-exchange using finite element method in a given specimen.
The objectives set for this programming project are listed below: 
- Calculate view factors, which determine the multipliers for thermal radiation. 
- Development of a Newton-Raphson solver for the boundary value problem with appropriate quadrature scheme. 
- Validate the solver using a one-dimensional steady-state configuration with heat radiation using a solution provided in literature.

## Solution

<div align="center">
  <img src="img/Pasted image 20260407152308.png" alt="Process in a finite element method based analysis" width="500">
  <p><em>Fig. 2: Process in a finite element method based analysis.</em></p>
</div>

Finite element method based analysis could be split into several sub-tasks or routines as shown in Figure 2[^2]. These tasks could be grouped into three broad categories:
- Pre-processing,
- Processing, and
- Post-processing.

Here, the definition of geometry as well as its subsequent meshing is handled using a software called GMsh. GMsh offers the ability to export the mesh in a wide range of supported formats, which meant that the pre-processing module required the creation of a parser for a specific mesh format. The processing tasks, which involve computation of gauss points, weights for quadrature, assembling the overarching system to be solved, handling boundary conditions in those global systems, were handled using `NumPy` and custom built OOP interfaces in Python. `Matplotlib` was used to generate post-processing information including temperature distribution plots after the analysis. 

Since the computations involved geometric viewfactor calculations in order to account for the arrangement of the two bodies in the system under consideration, a ray-tracing library was required. Even for a discretized system required by a finite element analysis, ray-tracing kernels could be used to determine which of the relevant "elements" can "see" each other. For this purpose, Intel® Corporation’s Embree kernels were employed under
Apache 2.0 license. 

## Results

To demonstrate the steady-state solving capabilities of the solver with multiple essential boundary conditions, consider a square plate of unit thickness and size 1 m, is subjected to isothermal boundary conditions of 100 $^{\circ}$C on all sides except the top side which is subjected to 500 $^{\circ}$C. If the thermal conductivity of the material is constant and equal to 10 W/m $^{\circ}$C, the resultant temperature distribution upon analysis can be seen here in Figure 3.

<div align="center">
  <img src="img/Pasted image 20260407153658.png" alt="The temperature distribution as generated by the code" width="500">
  <p><em>Fig. 3: The temperature distribution as generated by the code.</em></p>
</div>
Individual components of the Python interface were tested using `pytest` module.

## Links

- Repository: [git/radiative-heat-fem](https://gitlab.com/mukund-yedunuthala/radiative-heat-fem)
- [Link to Documentation](https://mukundyedunuthala.page/docs/radiative-heat-fem/)

## References

[^1]: Bejan A. Heat transfer: evolution, design and performance. Hoboken, NJ: John Wiley & Sons, Inc.; 2023.
[^2]: Nithiarasu, P. & Lewis, Roland & Seetharamu, K.N.. (2015). Fundamentals of the finite element method for heat and mass transfer.
