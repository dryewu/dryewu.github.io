---
layout: page
permalink: /publications/
title: PIBLICATIONS
description: My research interest is developing novel Computational Neuroimaging methods, including Quantitative Neuroimaging, Connectome Mapping, and Machine Learning, which dedicated to propose the most straightforward and robust solutions for real scientific issues. See my [Google Scholar Citations Profile](https://scholar.google.com/citations?user=soMcNA8AAAAJ&hl=zh-CN) for full publications list.

years: [2022,2021,2020,2019,2018,2017]
nav: false
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
