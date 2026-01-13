---
layout: page
permalink: /exp/
title: Experience
description: Research Experience  
nav: true
nav_order: 6
---

<!-- pages/research.md -->
<div class="exp">
{% assign sorted_projects = site.research | sort: "importance" %}

  <!-- Generate cards for each project -->
  <div class="container">
    <div class="row row-cols-1">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
    </div>
  </div>
</div>
