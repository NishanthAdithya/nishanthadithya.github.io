---
layout: page
permalink: /research/
title: Research
description: Documentation of my research experience.
nav: true
nav_order: 6
---

<div class="research">
  {% assign sorted_exp = site.exp | sort: "importance" %}
  <div class="container">
    <div class="row row-cols-1">
      {% for item in sorted_exp %}
        {% include projects.liquid project=item %}
      {% endfor %}
    </div>
  </div>
</div>
