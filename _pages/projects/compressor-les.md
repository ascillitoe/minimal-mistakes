---
title: "Large Eddy Simulation for Turbomachinery"
permalink: /projects/les-of-transitional-compressors
layout: single
author_profile: true
toc: true
classes: wide
excerpt: Towards predictive eddy resolving simulations of gas turbine compressors with an industrial CFD code.  
header:
    overlay_image: /assets/images/comp_les_header.png
    overlay_filter: 0.35
    actions:
    - label: "<i class='fas fa-download'></i> Get thesis"
      url: "https://www.repository.cam.ac.uk/handle/1810/270030"
---

Computational fluid dynamics (CFD) simulations play an important role in the design of modern aircraft. They are used to predict the flow around and through an aircraft, ultimately helping engineers design more efficient aircraft. The turbulence models used in such simulations are typically calibrated on relatively simple flows, and struggle to correctly account for the complex flow physics occuring in aeronautical applications.

{% include figure.html
            image_path="assets/images/posts/comp_les/aircraft_cfd.jpg"
            alt="aircraft_cfd"
            width = "50%"
            caption="Figure 1: A CFD simulation of an aircraft. <br>Source: DLR, CC-BY 3.0."%}


A potentially more accurate family of methods are eddy resolving simulations, where 
turbulent structures are *simulated* (instead of *modelled*). Such approaches are significantly more expensive computationally, but are becoming more achievable due to ever increasing advances in computing power. A compromise between the two families of approaches is *Large Eddy Simulation* (LES). Here, the large energy containing turbulent structures, which are difficult to model, are simulated. Whereas the smallest structures, which are expensive to simulate yet easy to model, are modelled.
  
<figure>
    <div style="display:flex">
        <div style="flex:1">
            <figure>
<img src="../../assets/images/posts/comp_les/hill_rans.png" style="width:95%">
                <figcaption><center>a) Modelled</center></figcaption>
            </figure>
        </div>
        <div style="flex:1">
            <figure>
<img src="../../assets/images/posts/comp_les/hill_les.png" style="width:95%">
                <figcaption><center>b) Simulated</center></figcaption>
            </figure>
        </div>
    </div>
    <figcaption><center>Figure 2: CFD simulations of a periodic hill, with turbulence either modelled or simulated. </center></figcaption>
</figure>

My PhD [project](https://www.repository.cam.ac.uk/handle/1810/270030) involved working with [Rolls-Royce](https://www.rolls-royce.com/products-and-services/civil-aerospace.aspx) to examine the feasibility of modifying an industrial CFD code, in order to run high fidelity Large Eddy Simulation of flows typical of those seen in aero-engine compressors. The project, supervised by [Prof. Paul Tucker](https://www.murrayedwards.cam.ac.uk/fellows/professor-paul-g-tucker) at the University of Cambridge, was broadly split into three parts. These are described in more detail in the following three sections.

{% include figure.html
            image_path="assets/images/posts/comp_les/trent_xwb.png"
            alt="trent_xwb"
            width = "45%"
            caption="Figure 3: A modern gas-turbine aero-engine, the Trent XWB."%}

## 1. Modifying an industrial CFD code

Aerospace companies have years, if not decades, of knowledge and experience embedded within their CFD codes. Therefore, it is desirable for companies to be able to extend their existing codes for CFD methods such as LES. This is challenging, since codes developed with turbulence modelling in mind are usually quite numerically dissiptive. This aids convergence to steady-state solutions, but in an LES context it has the undesirable effect of draining energy from the turbulent structures.   

<figure>
    <div style="display:flex">
        <div style="flex:1">
            <figure>
<img src="../../assets/images/posts/comp_les/FIT_high.png" style="width:60%">
                <figcaption><center>a) High smoothing</center></figcaption>
            </figure>
        </div>
        <div style="flex:1">
            <figure>
<img src="../../assets/images/posts/comp_les/FIT_low.png" style="width:60%">
                <figcaption><center>b) Low smoothing</center></figcaption>
            </figure>
        </div>
    </div>
    <figcaption><center>Figure 4: LES of forced isotropic turbulence, with two different levels of numerical smoothing. </center></figcaption>
</figure>

To avoid excessive numerical dissipation, one option is to lower the amount of smoothing, as is done for the canonical test case above. But, lower it too much and the opposite problem occurs, with excessive numerical dispersion (oscillations) occuring in the flow. Alternatively, one can increase the order of the spatial discretisations. However, this increases the communication required between computational grid points, which is undesirable for a code which must be parallelised across 1000's of processor cores. To tackle this issue, we instead implemented a novel adaptive smoothing scheme. This adjusts the smoothing locally, so that *just enough* smoothing is used to prevent spurious oscillations. This enabled a mature industrial CFD code to accurately run large LES simulations, with minimal tuning required.

## 2. Laminar to turbulence transition

A particular challenge for CFD computations of aero-engines compressors is laminar to turbulent transition. This often occurs in the early blade rows, and can have a significant influence on the efficiency of the compressor. Transition models can struggle to correctly capture the complex mechanisms causing laminar flows to transition to turbulencce
 
For transitional flows, SGS models...

With state-of-the-art SGS model, can simulate complex transition mechanisms

Effect of incoming turbulence etc


## 3. Towards real compressor flows


