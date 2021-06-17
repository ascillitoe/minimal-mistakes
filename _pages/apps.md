---
title: "Apps"
permalink: /apps/
layout: splash
author_profile: false

header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/code_header.jpg
excerpt: Have a go yourself with my interactive apps!

feature_row:
  - image_path: /assets/images/posts/ridge_app.png
    alt: "Dimension Reduction"
    title: "Tackling the Curse of Dimensionality"
    excerpt: "Performing data-driven dimension reduction with the equadratures package. Upload your own data or try an example dataset!"
    url: "https://reduce.ascillitoe.com/datadriven"
    btn_class: "btn--primary3"
    btn_label: "Load" 
  - image_path: /assets/images/posts/flowfield_app.png
    alt: "Rapid CFD"
    title: "Rapid Flowfield Predictions"
    excerpt: "Exploiting polynomial ridge functions for design exploration and rapid flowfield estimation of an airfoil. Predictive accuracy is competitive with a state-of-the-art convolutional neural network."
    url: "https://reduce.ascillitoe.com/flowfield"
    btn_class: "btn--primary3"
    btn_label: "Load"
---

These apps are hosted on Heroku dyno's with limited resources. Please try again later if they are too slow!

{% include feature_row %}
