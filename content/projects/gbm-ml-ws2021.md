+++
title = "Gradient Boosting Machine with Local Regression weak learner"
description = "Demonstrative project to construct a locally weighted regression based gradient boosting machine to predict material properties."
weight = 3

[extra]
local_image = "img/proj_pppws21_tn.png"
+++

#### Repository: [https://gitlab.com/mukund-yedunuthala/ppp-ws21-22](https://gitlab.com/mukund-yedunuthala/ppp-ws21-22)
#### Documentation: [https://mukund-yedunuthala.gitlab.io/ppp-ws21-22/](https://mukund-yedunuthala.gitlab.io/ppp-ws21-22/)

## Summary
The promise of applications of statistical learning in materials science could be summarized in its potential to move away from an Edisonian approach -- that is, to avoid a tedious trial-and-error discovery. Data-driven paradigms in materials science allow one to develop efficient, effective methods to generate, manage, and utilize relevant information.

Machine learning, or statistical learning, as a research area enables conception of models that
can learn from available data and situations to aid materials research, and discovery. They 
could be classified into two broad classes: *supervised* and *unsupervised* learning. Several 
approaches are available that could predict phase diagrams, crystal structures, and other materials
properties, as well as energy functionals or interatomic potentials. These algorithms use available data,
termed training data, and attempt to identify an underlying pattern, or function, to make near-accurate
predictions. In supervised learning, one has access to output values of training data as well, which 
makes the identification of the underlying pattern in output data the focus. Whereas, in unsupervised learning,
output values are absent from the training data. Therefore, the focus lies on identification of patterns within
the input data.


This project attempts to demonstrate a supervised learning approach to predict bulk and shear moduli for 
polycrystalline inorganic compounds. The training data is obtained from The Materials Project initiative.
This approach utilizes the benefits derived from a combination of 
multivariate local polynomial regression and gradient boosting machine algorithms. The former 
entails a series of weighted regressions to identify a smoothed curve, whereas the latter iteratively
assembles a predictor that minimizes a pre-defined loss function.
