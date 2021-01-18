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
## Under Review
{% endif %}

{% for publi in site.data.publist %}
{% if publi.year %}{% else %}

{% assign bibtest = false %}
{% if publi.url %}
{% assign bibfile = "/papers/" | append:  publi.url  | append: ".txt" %}
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
## Journal Papers and Proceedings 
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
{% if publi.year == myyear.year %}


{% assign bibtest = false %}
{% if publi.url %}
{% assign bibfile = "/papers/" | append:  publi.url  | append: ".txt" %}
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
{% endfor %}

{% endfor %}

