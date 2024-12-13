+++
title = "Gradient Boosting Machine with Local Regression weak learner"
date = 2022-03-27
updated = 2024-12-13

description = "Demonstrative project to construct a locally weighted regression based gradient boosting machine to predict material properties."
weight = 4
[taxonomies]
tags = ["Python", "Academia"]

[extra]
local_image = "img/proj_pppws21_tn.png"
+++
#### Repository: [git/gbm-local-regression](https://gitlab.com/mukund-yedunuthala/gbm-local-regression)
#### Documentation: [https://docs.mukund-yedunuthala.de/gbm-local-regression/](https://docs.mukund-yedunuthala.de/gbm-local-regression/)


## Summary
The potential of applying statistical learning in materials science is in moving away from the Edisonian approach, avoiding tedious trial-and-error discovery. Data-driven paradigms in materials science enable one to develop efficient, effective methods for generating, managing and utilizing relevant information.


Machine learning, or statistical learning, as a research area enables the creation of models that can 
learn from available data and situations to aid in materials research and discovery.  

These models can be categorized into two broad classes:"supervised" and "unsupervised" learning. Various methods are available that can predict phase diagrams, crystal structures, and other materials.

Properties, energy functionals, and interatomic potentials are analyzed by algorithms that use 
available data, known as training data, to identify patterns and functions that can make near-accurate
predictions. In supervised learning, output values of training data are also accessible, making the identification of the underlying  pattern in output data the primary objective. In unsupervised
learning, output values are not present in the training data. 
Consequently, the primary focus is on identifying patterns within the input data.

This project attempts to demonstrate a supervised learning approach to predict bulk and shear moduli for 
polycrystalline inorganic compounds. The training data is obtained from The Materials Project initiative.
This approach utilizes the benefits derived from a combination of 
multivariate local polynomial regression and gradient boosting machine algorithms. The former 
entails a series of weighted regressions to identify a smoothed curve, whereas the latter iteratively
assembles a predictor that minimizes a pre-defined loss function.
