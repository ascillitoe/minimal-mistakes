---
title: "Data-driven Turbulence Modelling"
permalink: /projects/ddrans-with-Mondrian-Forests
layout: single
author_profile: true
toc: true
excerpt: Augmenting turbulence model predictions with Mondrian forests.  
header:
    overlay_image: /assets/images/mondrian_header.jpg
    overlay_filter: 0.5
    actions:
    - label: "<i class='fas fa-download'></i> Get code"
      url: "https://github.com/ascillitoe/mondrian_turbulence"
---

This work examines the use of Mondrian forests for data-driven turbulence modelling, where a Reynolds-Averaged Navier-Stokes (RANS) turbulence model is augmented with data from high fidelity eddy resolving simulations. Replacing the more commonly used random forests with Mondrian forests provides principled uncertainty quantification. This is important, since the addition of a machine learning model adds an additional source of uncertainty, the uncertainty of the ML model itself. For use in an industrial setting, quantification of this uncertainty is essential, as the predictive capability of a data-driven model diminishes when predicting physics not seen during training. 

A python based framework is available [here](https://github.com/ascillitoe/mondrian_turbulence). The code trains random forests and Mondrian forests on high fidelity LES/DNS data. The trained models can then be used to predict turbulence parameters for a new RANS flowfield. For more details see:

Ashley Scillitoe, Pranay Seshadri, Mark Girolami,
*Uncertainty quantification for data-driven turbulence modelling with mondrian forests*,
Journal of Computational Physics,
2021,
**430**(1), 110116,
ISSN 0021-9991,
doi: [10.1016/j.jcp.2021.110116](https://doi.org/10.1016/j.jcp.2021.110116). 
arXiv: [2003.01968](http://arxiv.org/abs/2003.01968).
