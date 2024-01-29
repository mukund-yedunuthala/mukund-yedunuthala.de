+++
title = "Gradient Boosting Machine with Local Regression weak learner"
description = "Demonstrationsprojekt zur Konstruktion einer Gradient-Boosting-Maschine auf Basis der lokalen Regression für die Vorhersage von Materialeigenschaften."
weight = 3

[taxonomies]
tags = ["Python", "Academia"]

[extra]
local_image = "img/proj_pppws21_tn.png"
+++
#### Git-Repository: [git/gbm-local-regression](https://git.mukund-yedunuthala.de/mukund-yedunuthala/gbm-local-regression)
#### Dokumentation: [https://mukund-yedunuthala.gitlab.io/ppp-ws21-22/](https://mukund-yedunuthala.gitlab.io/ppp-ws21-22/)

## Überblick
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
