---
layout: page
title: people
permalink: /people/
description: (Updated in March 2025)
nav: true
nav_order: 7
display_categories: [professor, graduate, undergraduate] 
---
<div class="people">
  {%- if site.enable_people_categories and page.display_categories %}
  <!-- Display categorized people--> 
  {%- for category in page.display_categories %}
    {% capture localized_category %}people.categories.{{category}}{% endcapture %} 
    <div class="container mt-2 mb-3">
      <h2 class="category">{% t localized_category %}</h2>
      <hr>
      {%- assign categorized_members = site.people| where: "category", category -%}
      {%- assign sorted_members = categorized_members | sort: "importance" %} 
      <div class="grid">
        {%- for people in sorted_members -%}
          {% include people.html %}
        {%- endfor %}
      </div> 
     </div> 
    {% endfor %}
  {%- else -%}
  <!-- Display people without categories -->
    {%- assign sorted_people= site.people| sort: "importance" -%}
    <!-- Generate cards for each project --> 
    <div class="grid">
      {%- for people in sorted_people-%}
        {% include people.html %}
      {%- endfor %}
    </div> 
  {%- endif -%} 
</div> 

