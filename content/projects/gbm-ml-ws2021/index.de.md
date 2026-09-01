+++
title = "Application of statistical learning to predict material properties"
date = 2022-03-27
updated = 2026-04-07

description = "Demonstrationsprojekt zur Konstruktion einer Gradient-Boosting-Maschine auf Basis der lokalen Regression für die Vorhersage von Materialeigenschaften."
weight = 4
[taxonomies]
tags = ["Python", "Academia"]

[extra]
local_image = "projects/gbm-ml-ws2021/img/proj_pppws21_tn.png"
social_media_card = "img/social_cards/de_projects_gbm_ml_ws2021.jpg"
+++
This is a programming project to demonstrate that machine learning approaches could be used to harvest traits present in some data to aid materials research. 

## Overview

Prima facie, properties like the elastic constants, i.e., the bulk and shear moduli, could be used to correlate with wide range of materials and their characteristic properties. Theoretical models limit themselves to specific subsets. This study attempts to construct a locally weighted regression based gradient boosting machine to predict material properties.

The idea is to construct a statistical learning model that utilizes gradient boosting machine
framework with a multivariate local polynomial regression base-learner to predict
material properties such as bulk (K) and shear (G) moduli.

The objectives of this programming project, therefore, were established:
- Handle integration with The Materials Project API for data. 
- Build pipelines to construct descriptors, i.e., generalized power means. 
- Train and predict Voigt-Reuss-Hill (VRH) averages of bulk and shear moduli.
- Validate using available data sourced from The Materials Project API.
- Screen for super-hard compounds using Vickers hardness parameter.

## Solution 

Materials Genome Initiative, founded in 2011 in the United States of America (USA) and touted to be an approach to promote collaboration between various disciplines, had focused on developing frameworks to accelerate discovery and deployment of advanced materials. One such projects undertaken by MGI is The Materials Project. It serves an open dataset that is accesible through multiple channels. The Materials API is a component of the materials project. It serves the required data over a REST API. 

The ratio of infinitesimal increase in pressure to its relative decrease of volume describes the bulk modulus of a substance, whereas shear modulus, also known as modulus of rigidity, provides a measure of shear stiffness of a substance through the ratio of shear stress to shear strain. This project focuses on Voigt-Reuss-Hill averages for the bulk and shear moduli. It is an empirical average has been deemed to provide a better represetation of the bulk and shear modulus of polycrystalline materials. The empirical averages of Voigt-Reuss-Hill average values are given by the equation:
$$
\begin{equation}
	2K_{VRH} = (K_V+K_R)
\end{equation}
$$
$$
\begin{equation}
	2G_{VRH} = (G_V+G_R)
\end{equation}
$$

## Implementation

This project could be broadly divided into two areas. 
- Pre-processing, i.e. sourcing of the data and making it viable to be processed by GBM implementation. 
- GBM implementation including the construction of weak learner, which in this case, uses multivariate local polynomial regression. 
All the modules were then written from scratch using `Python` and `NumPy`, including an accelerated local regression kernel using `Cython`, with an emphasis on OOP. 

The workflow in this programming project could be summarized as follows: 
- Acquire a valid API key that should be used for The Materials Project API. 
- Alter the input parameters file with parameters appropriate for the training. 
- Run the training file. 
- Use helper functions to access data that helps in interpretation.

This programming project succeeeds in learning the VRH averages of elastic bulk and shear moduli. The implementation targeted learning of $\log(K)$ and $\log(G)$ within a gradient boosting machine framework using multivariate local polynomial as the weak learner. 

## Results

<table>
  <tr>
    <td><img src="Pasted image 20260407200804.png" alt="" width="360"></td>
    <td><img src="Pasted image 20260407200841.png" alt="" width="360"></td>
  </tr>
</table>
<div align="center">
    <p><em>Fig. 1: Comparison of predictions of shear modulus and bulk modulus for compounds including quarternary systems.</em></p>
</div>
## Links

- **Repository**: [git/gbm-local-regression](https://gitlab.com/mukund-yedunuthala/gbm-local-regression)
- **Documentation**: [Link to Documentation](https://mukundyedunuthala.page/docs/gbm-local-regression/)
