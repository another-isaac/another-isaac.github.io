---
layout: page
title: Projects
permalink: /projects/
---

<ul class="entry-list">
  {%- for project in site.data.projects -%}
  <li class="project-item">
    <a class="project-title" href="{{ project.url }}" target="_blank" rel="noopener noreferrer">{{ project.title }}</a>
    <p class="entry-blurb">{{ project.blurb }}</p>
  </li>
  {%- endfor -%}
</ul>
