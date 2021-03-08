---
title: "Publications"
permalink: /publications/
layout: single
author_profile: true
classes: wide
header:
    overlay_image: /assets/images/library_header.jpg
    overlay_filter: 0.6
---

<style>
.img_box { grid-area: img; }
.main_box { grid-area: main; }

.grid-container {
  display: grid;
  grid-template-areas:
    'img main main main';
  grid-template-columns: 9.6em auto;
  grid-gap: 1em;
  padding: 0em;
}

.grid-container > div {
  padding: 0 0;
}

img {
  border-radius: 14px;
  margin-top:5px
}
</style>


{% assign yeartest = true %}
{% for publi in site.data.publist %}
  {% if publi.year %}{% else %}
   {% assign yeartest = false %}
  {% endif %}
{% endfor %}

{% if yeartest == false %}
## Preprints
{% endif %}

{% for publi in site.data.publist %}
{% if publi.year %}{% else %}

{% assign bibtest = false %}
{% if publi.url %}
{% assign bibfile = "/papers/" | append:  publi.url  | append: ".bib" %}
{% for file in site.static_files %}
  {% if file.path contains bibfile %}
   {% assign bibtest = true %}
  {% endif %}
{% endfor %}
{% endif %}

<div class="box">

<div class="grid-container">

<div class="img_box">
{% if publi.image %}
 <img src="{{ site.url }}{{ site.baseurl }}/assets/images/pubs/{{ publi.image }}" />

{% endif %}
</div>

<div class="main_box">
 <strong> {{ publi.title }}</strong><br/>
 {{ publi.authors | replace_first: 'A. Scillitoe', '<b>A. Scillitoe</b>'}}<br/>
 {% if publi.journal %}Under review at <i>{{ publi.journal }}</i>,{% endif %} {% if publi.arxiv %} arXiv {{ publi.arxiv }} {% endif %}<br/>
 {% if publi.url %}<a href="{{ site.url }}{{ site.baseurl }}/assets/papers/{{ publi.url }}.pdf" class="btn btn--success btn--small">PDF</a>{% endif %}
 {% if publi.arxiv %}<a href="https://arxiv.org/abs/{{ publi.arxiv }}" class="btn btn--warning btn--small">ARXIV</a> {% endif %}
 {% if bibtest %}<a href="{{ site.url }}{{ site.baseurl }}/assets/papers/{{ publi.url }}.bib" class="btn btn--primary3 btn--small">BIB</a> {% endif %}

{% if publi.abstract %}
<div class="wrap-collabsible"> 
  <input id="collapsible1-{{forloop.index}}" class="toggle" type="checkbox"> 
  <label for="collapsible1-{{forloop.index}}" class="lbl-toggle" tabindex="0">Abstract</label>
  <div class="collapsible-content">
   <div class="content-inner"> {{publi.abstract}} </div>
  </div>
</div>
{% endif %}
</div>

</div> 
</div> 
{% endif %}
{% endfor %}



{% if site.group_pub_by_year == true %}{% else %}
## Journal Papers
{% endif %}

{% for myyear in site.data.years %}

{% assign yeartest = false %}
{% for publi in site.data.publist %}
  {% if publi.year == myyear.year %}
   {% assign yeartest = true %}
  {% endif %}
{% endfor %}

{% if site.group_pub_by_year == true %}
{% if yeartest == true %}
### {{ myyear.year }}
{% endif %}
{% endif %}

{% for publi in site.data.publist %}
{% if publi.journal %}

{% if publi.year == myyear.year %}


{% assign bibtest = false %}
{% if publi.url %}
{% assign bibfile = "/papers/" | append:  publi.url  | append: ".bib" %}
{% for file in site.static_files %}
  {% if file.path contains bibfile %}
   {% assign bibtest = true %}
  {% endif %}
{% endfor %}
{% endif %}


<div class="box">
<div class="grid-container">

<div class="img_box">
  {% if publi.image %}
   <img src="{{ site.url }}{{ site.baseurl }}/assets/images/pubs/{{ publi.image }}"/>
  {% endif %}
</div>

<div class="main_box">
  <b>{{ publi.title }}</b><br/>
  {{ publi.authors | replace_first: 'A. Scillitoe', '<b>A. Scillitoe</b>'}}<br/>
  <i>{{ publi.journal }}</i>{% if publi.info %}, {{publi.info}}{% endif %} {% if publi.year %}({{publi.year}}){% endif %}<br/>
  {% if publi.url %}<a href="{{ site.url }}{{ site.baseurl }}/assets/papers/{{ publi.url }}.pdf" class="btn btn--small btn--success">PDF</a>{% endif %} 
  {% if publi.doi %}<a href="http://dx.doi.org/{{ publi.doi }}" class="btn btn--small btn--danger">DOI</a> {% endif %}
  {% if publi.arxiv %}<a href="https://arxiv.org/abs/{{ publi.arxiv }}" class="btn btn--warning btn--small">ARXIV</a> {% endif %}
  {% if bibtest %}<a href="{{ site.url }}{{ site.baseurl }}/assets/papers/{{ publi.url }}.bib" class="btn btn--primary3 btn--small">BIB</a> {% endif %}

{% if publi.abstract %}
<div class="wrap-collabsible"> 
  <input id="collapsible2-{{forloop.index}}" class="toggle" type="checkbox"> 
  <label for="collapsible2-{{forloop.index}}" class="lbl-toggle" tabindex="0">Abstract</label>
  <div class="collapsible-content">
   <div class="content-inner"> {{publi.abstract}} </div>
  </div>
</div>
{% endif %}
</div>

</div>
</div>

{% endif %}
{% endif %} [//]: # ends if statement on line 117

{% endfor %}

{% endfor %}


{% if site.group_pub_by_year == true %}{% else %}
## Conference Proceedings
{% endif %}

{% for myyear in site.data.years %}

{% assign yeartest = false %}
{% for publi in site.data.publist %}
  {% if publi.year == myyear.year %}
   {% assign yeartest = true %}
  {% endif %}
{% endfor %}

{% if site.group_pub_by_year == true %}
{% if yeartest == true %}
### {{ myyear.year }}
{% endif %}
{% endif %}

{% for publi in site.data.publist %}
{% if publi.journal %}{% else %}

{% if publi.year == myyear.year %}


{% assign bibtest = false %}
{% if publi.url %}
{% assign bibfile = "/papers/" | append:  publi.url  | append: ".bib" %}
{% for file in site.static_files %}
  {% if file.path contains bibfile %}
   {% assign bibtest = true %}
  {% endif %}
{% endfor %}
{% endif %}


<div class="box">
<div class="grid-container">

<div class="img_box">
  {% if publi.image %}
   <img src="{{ site.url }}{{ site.baseurl }}/assets/images/pubs/{{ publi.image }}"/>
  {% endif %}
</div>

<div class="main_box">
  <b>{{ publi.title }}</b><br/>
  {{ publi.authors | replace_first: 'A. Scillitoe', '<b>A. Scillitoe</b>'}}<br/>
  <i>Proceedings of {{ publi.conference }}</i>{% if publi.info %}, {{publi.info}}{% endif %} {% if publi.year %}({{publi.year}}){% endif %}<br/>
  {% if publi.url %}<a href="{{ site.url }}{{ site.baseurl }}/assets/papers/{{ publi.url }}.pdf" class="btn btn--small btn--success">PDF</a>{% endif %} 
  {% if publi.doi %}<a href="http://dx.doi.org/{{ publi.doi }}" class="btn btn--small btn--danger">DOI</a> {% endif %}
  {% if publi.arxiv %}<a href="https://arxiv.org/abs/{{ publi.arxiv }}" class="btn btn--warning btn--small">ARXIV</a> {% endif %}
  {% if bibtest %}<a href="{{ site.url }}{{ site.baseurl }}/assets/papers/{{ publi.url }}.bib" class="btn btn--primary3 btn--small">BIB</a> {% endif %}

{% if publi.abstract %}
<div class="wrap-collabsible"> 
  <input id="collapsible2-{{forloop.index}}" class="toggle" type="checkbox"> 
  <label for="collapsible2-{{forloop.index}}" class="lbl-toggle" tabindex="0">Abstract</label>
  <div class="collapsible-content">
   <div class="content-inner"> {{publi.abstract}} </div>
  </div>
</div>
{% endif %}
</div>

</div>
</div>

{% endif %}
{% endif %} [//]: # ends if statement on line 117

{% endfor %}

{% endfor %}


## Doctoral Thesis

<div class="box">
<div class="grid-container">

<div class="img_box">
 <img src="{{ site.url }}{{ site.baseurl }}/assets/images/pubs/thesis_img.png" />
</div>

<div class="main_box">
 <strong> Towards Predictive Eddy Resolving Simulations for Gas Turbine Compressors</strong><br/>
 <b>A. Scillitoe</b><br/>
  <i>PhD Thesis</i>, University of Cambridge (2017)<br/>
 <a href="{{ site.url }}{{ site.baseurl }}/assets/papers/scillitoe_thesis.pdf" class="btn btn--success btn--small">PDF</a>
 <a href="http://dx.doi.org/10.17863/CAM.16871" class="btn btn--small btn--danger">DOI</a>
 <a href="{{ site.url }}{{ site.baseurl }}/assets/papers/scillitoe_thesis.bib" class="btn btn--primary3 btn--small">BIB</a>

<div class="wrap-collabsible"> 
  <input id="collapsible3-{{forloop.index}}" class="toggle" type="checkbox"> 
  <label for="collapsible3-{{forloop.index}}" class="lbl-toggle" tabindex="0">Abstract</label>
  <div class="collapsible-content">
   <div class="content-inner"> 
This thesis aims to explore the potential for using large eddy simulation (LES) as a predictive tool for gas-turbine compressor flows. Compressors present a significant challenge for the Reynolds Averaged Navier-Stokes (RANS) based CFD methods commonly used in industry. RANS models require extensive calibration to experimental data, and thus cannot be used predictively. This thesis explores how LES can offer a more predictive alternative, by exploring the sensitivity of LES to sources of uncertainty. Specifically, the importance of the numerical scheme, the Sub-Grid Scale (SGS) model, and the correct specification of inflow turbulence is examined. The sensitivity of LES to the numerical scheme is explored using the Taylor-Green vortex test case. The numerical smoothing, controlled by a user defined smoothing constant, is found to be important. To avoid tuning the numerical scheme, a novel scheme, the LAS with windowing (LASW) scheme, is introduced. The LASW scheme is used to perform LES on a compressor cascade, and results are found to be in close agreement with direct numerical simulations. Complex transition mechanisms, combining characteristics of both natural and bypass modes, are observed on the pressure surface. On the suction surface, separation induced transition occurs. The results demonstrate that, with the LASW scheme and a suitable SGS model, LES can be used predictively in compressor flows. In order to be predictive, the accurate specification of inflow conditions was shown to be just as important as the numerics. RANS models are shown to over-predict the extent of the three dimensional separation in the endwall - suction surface corner. LES is used to examine the challenges for RANS in this region. The LES shows that it is important to accurately capture the suction surface transition location, with early transition leading to a larger endwall separation. Large scale aperiodic unsteadiness is also observed in the endwall region. Additionally, turbulent anisotropy in the endwall - suction surface corner is found to be important. Adding a non-linear term to the RANS model leads to turbulent stresses that are in better agreement with the LES. This results in a stronger corner vortex which is thought to delay the corner separation. The addition of a corner fillet reduces the importance of anisotropy, thereby reducing the uncertainty in the RANS prediction.
   </div>
  </div>
</div>
</div>

</div> 
</div> 
