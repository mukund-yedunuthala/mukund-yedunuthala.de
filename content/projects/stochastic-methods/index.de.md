+++
title = "Stochastic Modeling in R"
description = "This ensemble study explores stochastic modeling techniques in the context of materials science, using R and RStudio for implementation."
date = 2021-03-21
updated = 2026-04-07
weight = 4
author = "Mukund Yedunuthala"

[taxonomies]
tags = ["R", "Academia"]

[extra]
local_image = "projects/stochastic-methods/img/stc-methd.png"
show_remote_changes = true
social_media_card = "img/social_cards/de_projects_stochastic_methods.jpg"
+++

<table>
  <tr>
    <td><img src="https://gitlab.com/mukund-yedunuthala/stome-project-ws2020/-/raw/master/image1_09.png?ref_type=heads&inline=true" alt="" width="360"></td>
    <td><img src="https://gitlab.com/mukund-yedunuthala/stome-project-ws2020/-/raw/master/image2_09.png?ref_type=heads&inline=true" alt="" width="360"></td>
  </tr>
</table>
<div align="center">
    <p><em>Fig. 1: 2D random set distributions resembling microstructures</em></p>
</div>
This ensemble study explores stochastic modeling techniques in the context of materials science, using R and RStudio for implementation.
## Overview

This programming project explores applications of stochastic geometry techniques to model and analyse features resembling microstructures of materials. The emphasis lies on implementation in R and best practices of developing such models using RStudio. This work involves image-based analysis, probabilistic modeling, and statistical simulation to investigate the geometric and topological properties of random material structures. This ensemble consists of 4 tasks:
- Morphological Analysis Using Minkowski Functionals,
- Morphological Openings and Boolean Model Evaluation,
- Wicksell’s corpuscle problem, and
- Monte Carlo Estimation of Quermass Densities.

This project was a part of the course module "Stochastic methods for material scientists" in TU Bergakademie Freiberg. The project was expected to be delivered within 2 weeks, and without any assistance from productivity enhancement tools. It was intended to be an entry point to stochastic modeling and R programming language. 

## Tasks

**Morphological analysis using Minkowski functionals**: Given realizations of 2D sets which are similar in shape to microstructures of materials, and are of compact, non-convex sets, the task was to evaluate Minkowski functionals (area, perimeter, Euler characteristic) using R and perform a comparative analysis with appropriate plots. This exercise is intended to explain the characteristics of structural complexity by comparing connectivity and homogeneity across different random set realizations.

**Morphological openings and Boolean model evaluation**: This two-part task is a part of microstructure characterization pipeline. First, morphological openings are applied to a random 2D set similar to those described earlier. By iteratively increasing the size of a disc-shaped structuring element, the image is effectively 'filtered'. Upon realization of physical scale of features, a boolean model is constructed where objects are placed at random locations. To ensure that the model is a valid representation, Monte Carlo simulations are performed. The intention is to introduce the idea that a combination of these techniques could be used to predict material behaviour under different conditions. 

**Wicksell’s corpuscle problem**: Wicksell’s corpuscle problem (formulated by Sven Wicksell in 1925) asks: **"If we have a volume containing spheres of unknown sizes, and we take a random 2D slice, can we determine the size distribution of the 3D spheres based only on the 2D circles we see?"** The task is to demonstrate **Saltykov method**, which is a discrete numerical solution to the **Abel-type integral equation** that Wicksell derived. 

<div align="center">
  <img src="https://gitlab.com/mukund-yedunuthala/stome-project-ws2020/-/raw/master/image3_09.png?ref_type=heads" alt="Wicksell’s corpuscle problem image" width="300">
  <p><em>Fig. 2: Wicksell’s corpuscle problem image</em></p>
</div>

**Monte Carlo estimation of Quermass densities**: The idea is to conduct a **Monte Carlo study** to estimate the **Quermass densities**: the area fraction, boundary length, and Euler characteristic. By varying the underlying Poisson intensity (λ), the statistical 'crowding' of particles impacts the bulk geometric properties of the material was quantified. Box plots and **standard deviation analysis** were used to assess the precision of these geometric estimators, which is critical for determining how many image samples are needed to get a reliable measurement of a real material's microstructure. The analysis was performed over **Matérn Type III Hard-Disc Model** to simulate realistic, non-overlapping particle distributions.

## Tools & Techniques

- R & RStudio
- `spatstat`, `EBImage`, `ggplot2`, `dplyr`, `stats`

## Outcome

The project successfully demonstrates the potential of stochastic methods and spatial statistics, implemented in R, to quantify and interpret complex structural behaviors in random materials. This provides a foundation for predictive modeling and digital material design workflows.
<div align="center">
  <img src="https://gitlab.com/mukund-yedunuthala/stome-project-ws2020/-/raw/master/task01/01_01_all.png?ref_type=heads" alt="Cluster of images showing plots of Minkowski functions for a 2D random set distribution" width="500">
  <p><em>Fig. 3: Morphological analysis using Minkowski functionals</em></p>
</div>
<table>
  <tr>
    <td align="center">
      <b>Original Image</b><br>
      <img src="https://gitlab.com/mukund-yedunuthala/stome-project-ws2020/-/raw/master/task02/02_a1.png" width="100%">
    </td>
    <td align="center">
      <b>After 1 application cycle</b><br>
      <img src="https://gitlab.com/mukund-yedunuthala/stome-project-ws2020/-/raw/master/task02/02_a2.png" width="100%">
    </td>
  </tr>
  <tr>
    <td align="center">
      <b>After 2 cycles</b><br>
      <img src="https://gitlab.com/mukund-yedunuthala/stome-project-ws2020/-/raw/master/task02/02_a3.png" width="100%">
    </td>
    <td align="center">
      <b>After 3 cycles</b><br>
      <img src="https://gitlab.com/mukund-yedunuthala/stome-project-ws2020/-/raw/master/task02/02_a4.png" width="100%">
    </td>
  </tr>
</table>
<div align="center">
 <p><em>Fig. 4: Progression of Morphological openings</em></p>
</div>


## Links

Source code: [GitLab](https://gitlab.com/mukund-yedunuthala/stome-project-ws2020)
