+++
title = "Modeling of radiative heat-exchange using Finite Element Method (FEM)"
description = "Finite-Elemente-Methode basierender Solver für ein mathematisches Modell der Wärmeübertragung, bestehend aus einem System, das zwischen Leitung und Strahlung gekoppelt ist."
date = 2022-10-15
updated = 2024-12-13
weight = 3

[taxonomies]
tags = ["Python", "Academia"]

[extra]
local_image = "img/proj_pppss22_tn.png"
+++

#### Git-Repository: [git/radiative-heat-fem](https://gitlab.com/mukund-yedunuthala/radiative-heat-fem)
#### Documentation: [https://docs.mukund-yedunuthala.de/radiative-heat-fem/](https://docs.mukund-yedunuthala.de/radiative-heat-fem/)

## Überblick
The energy transport between material bodies is characterized by a section of science known as heat transfer. The three modes of such an energy transfer, which occurs primarily due to a difference in the temperature, are: conduction, convection, and radiation.

To describe briefly, conduction mode of heat transfer describes the energy transport that occurs owing to an exchange of energy between molecules, or subatomic particles, without actually moving. As such, the characteristics of such a transfer depend upon the medium of transfer itself.

This programming project attempts to model instances of each of these heat transfers in order to evaluate the temperature distribution. These governing equations are characterized in their weak integral formulations, which in turn are discretized using Galerkin's approach to develop a finite element method-based model to evaluate said temperature distribution.

