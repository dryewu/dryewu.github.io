---
layout: page
permalink: /publications/
title: Publications
description: Research Paper is an output of new findings, and original positive or negative results concerning the existing method, allowing science to be advanced.
years: [2022,2021,2020,2019,2018,2017]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
