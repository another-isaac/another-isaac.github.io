---
layout: page
title: Projects
permalink: /projects/
---

<ul class="project-list">
  {%- for project in site.data.projects -%}
  <li class="project-item">
    <a class="project-title" href="{{ project.url }}" target="_blank" rel="noopener noreferrer">{{ project.title }}</a>
    <p class="project-blurb">{{ project.blurb }}</p>
  </li>
  {%- endfor -%}
</ul>
