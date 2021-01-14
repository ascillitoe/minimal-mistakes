---
title: "Projects"
permalink: /projects/
layout: splash
author_profile: false

header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/code_header.jpg
excerpt: My research is focused on applying data-driven methods to aeronautical problems.  

feature_row:
  - image_path: /assets/images/posts/2Dsplit.gif
    alt: "Machine Learning"
    title: "Machine Learning with Polynomials"
    excerpt: "***Polynomial regression trees*** combine decision tree learning with polynomial regression, resulting in accurate yet interpretable models. The resulting models can be used for a wide range of tasks, from traditional supervised learning to uncertainty quantification."
    url: "/projects/polynomial-regression-trees/"
    btn_class: "btn--primary3"
    btn_label: "Learn more"
  - image_path: /assets/images/posts/endwall_les.png
    alt: "Turbulence Modelling"
    title: "Data-driven Turbulence Modelling"
    excerpt: "Mondrian forests, trained on high fidelity CFD data, are used to augment turbulence models. Their uncertainty estimates provide crucial information on the suitability of the model, and the data used to train it."
    url: "/projects/ddrans-with-Mondrian-Forests"
    btn_class: "btn--primary3"
    btn_label: "Learn more"
  - image_path: /assets/images/posts/hi_dim.jpeg
    alt: "Dimension Reduction"
    title: "Tackling the Curse of Dimensionality"
    excerpt: "Dimension reducing subspaces are shown to be a powerful tool for exploring high dimensional design spaces, providing important physical insights and allowing for in-depth analysis of uncertainties."
    url: "/posts/2020/dimension-reduction-for-probes/"
    btn_class: "btn--primary3"
    btn_label: "Learn more"      

feature_row2:
#  - image_path: /assets/images/posts/bayesian.png
#    alt: "Multi-Fidelity"
#    title: "Multi-fidelity Polynomials using Bayesian Statistics"
#    excerpt: "High fidelity data is often viewed simply as data used to validate cheaper low fidelity models. We introduce ***Bayesian polynomial chaos*** to exploit multi-fidelity data in a more symbiotic manner."
#    url: "/projects/bayesian-pce"
#    btn_class: "btn--primary3"
#    btn_label: "Learn more"
  - image_path: /assets/images/posts/rapid_cfd.png
    alt: "Rapid CFD"
    title: "Rapid Flowfield Predictions"
    excerpt: "Dimension reducing embedded ridge functions offer rapid flowfield predictions, with comparable accuracy to state-of-the-art deep learning methods, whilst being more interpretible and posessing baked-in uncertainty quantification."
    url: "/projects/rapid-cfd"
    btn_class: "btn--primary3"
    btn_label: "Learn more"
  - image_path: /assets/images/posts/suction.gif
    alt: "Large Eddy Simulation"
    title: "Large Eddy Simulation for Turbomachinery"
    excerpt: "My PhD involved working with Rolls-Royce to examine the feasability of modifying an industrial CFD code, in order to run high fidelity Large Eddy Simulations of the transitional flows in aero-engines."
    url: "/projects/les-of-transitional-compressors"
    btn_class: "btn--primary3"
    btn_label: "Learn more"
---

{% include feature_row %}
{% include feature_row id="feature_row2" %}
