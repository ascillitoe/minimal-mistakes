---
title: "Rapid Flowfield Predictions"
permalink: /projects/rapid-cfd
layout: single
author_profile: true
toc: false
classes: wide
excerpt: Embedding dimension reducing ridge functions for rapid data-driven flowfield predictions.
header:
    overlay_image: /assets/images/turbine_header.jpeg
    overlay_filter: 0.4
    actions:
    - label: "<i class='fas fa-download'></i> Get code"
      url: "https://github.com/ascillitoe/gaussian_flowfield_approx"
---

[//]: # ## Rapid Flowfield Prediction

Data-driven methods offer the possibility of replacing expensive computational simulations with cheaper approximations. In a range of fields, including uncertainty quantification, design optimisation, and sensitivity analysis, lower fidelity surrogate models (or emulators) are constructed from existing simulation data. Recently, supervised deep learning methods have seen increasing attention for this purpose. Deep learning architectures, routinely used in data mining, have been used with considerable success as a function approximation technique for high-dimensional physics derived datasets. For example, a convolutional neural network (CNN) can be used to learn a mapping between an object's geometric representation and the flowfield around it. 

However, despite the potential offered by CNN's for instant flowfield predictions, there are a number of barriers to their adoption in industry. Firstly, they introduce an additional source of error, the error in the CNN predictions. It is difficult to quantify or bound this error on *test data*, without running additional simulations. Secondly, deep neural networks such as CNN's are often criticised for being difficult to interpret.

In this project, we develop a new flowfield approximation framework which involves embedding ridge functions within the flowfield. We demonstrate this approach to have competitive predictive accuracy to a state-of-the-art CNN architecture. Additionally, the dimension reducing nature of the ridge functions allows for effective interpretation of the model (and data), whilst uncertainty quantification is achieved through the addition of various kernel functions. In our recent AIAA SciTech paper, we use Gaussian processes for the underlying ridge approximations:


Scillitoe, A., Seshadri, P. and Wong, C., 2021. *Instantaneous Flowfield Estimation with Gaussian Ridges.* In: AIAA SciTech. AIAA. Available at: <https://arc.aiaa.org/doi/abs/10.2514/6.2021-1138>.

As a more efficient alternative, we're currently exploring the use of orthogonal polynomials using our [equadratures](https://github.com/Effective-Quadratures/Effective-Quadratures) python library. See [this app](http://reduce.ascillitoe.com/) for an interactive example!

[//]: # ## Embedded Ridge Approximations

[//]: # ## Flowfield Reconstruction

[//]: # ## Predicting the Flow Around an Aerofoil
