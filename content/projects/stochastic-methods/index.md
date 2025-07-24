+++
title = "Stochastic Modeling in R"
description = "This study explores stochastic modeling techniques in the context of materials science, using R and RStudio for implementation."
date = 2021-03-21
updated = 2025-07-24
weight = 4

[taxonomies]
tags = ["R", "Academia"]

[extra]
local_image = "projects/stochastic-methods/img/stc-methd.png"
show_remote_changes = true
social_media_card = "img/social_cards/projects_stochastic_methods.jpg"
+++

### Overview:

This project applies stochastic geometry techniques to model and analyze microstructural features in materials. Implemented entirely in R using RStudio, the work involved image-based analysis, probabilistic modeling, and statistical simulation to investigate the geometric and topological properties of random material structures.

#### Key Contributions:

🔹 Task 1: Morphological Analysis Using Minkowski Functionals
- Analyzed 2D realizations of random sets.
- Applied Minkowski functionals (area, perimeter, Euler characteristic) to characterize structural complexity.
- Compared connectivity and homogeneity across different random set realizations.

🔹 Task 2: Morphological Openings and Boolean Model Evaluation
- Performed morphological openings to estimate shortest side lengths in grain-like structures.
- Proposed and validated two Boolean models using global envelope tests with 999 repetitions.
- Both models showed acceptable fit with p-values of 0.312 and 0.514.

🔹 Task 3: Wicksell Corpuscle Inverse Problem
- Used segmentation algorithms on 2D slices to infer 3D grain size distributions.
- Estimated volume fraction, specific surface area, and intensity of spherical inclusions.
- Provided statistical summaries and visualizations of the diameter distributions.

🔹 Task 4: Monte Carlo Estimation of Quermass Densities
- Simulated Matern III hard-disc models with varying Poisson intensities.
- Computed Quermass densities (area fraction, boundary length, Euler number) using Monte Carlo methods.
- Identified systematic increases in structural metrics with higher intensities.

### Tools & Techniques:
- R & RStudio
- `spatstat`, `EBImage`, `ggplot2`, `dplyr`, `stats`
- Morphological Image Processing
- Stochastic Modeling (Boolean and Matern Processes)
- Monte Carlo Simulations
- Global Envelope Testing

#### Outcome:

The project successfully demonstrates the potential of stochastic methods and spatial statistics, implemented in R, to quantify and interpret complex structural behaviors in random materials. This provides a foundation for predictive modeling and digital material design workflows.
