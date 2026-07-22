---
layout: page
title: Music
permalink: /music/
---

<ul class="music-list">
  {%- for jam in site.data.music -%}
  <li class="field-row music-item">
    {%- if jam.album_cover_url -%}
    <img class="music-cover" src="{{ jam.album_cover_url }}" alt="{{ jam.title }} cover art">
    {%- endif -%}
    <div class="music-info">
      <span class="music-title">{{ jam.title }}
        <a class="jam-link" href="{{ jam.youtube_url }}" target="_blank" rel="noopener noreferrer" aria-label="Watch on YouTube">&#9654;</a>
      </span>
      {%- if jam.date -%}
      <span class="music-date">{{ jam.date | date: "%b %-d, %Y" }}</span>
      {%- endif -%}
      {%- if jam.description -%}
      <p class="music-description">{{ jam.description }}</p>
      {%- endif -%}
      {%- if jam.genre_tags -%}
      <p class="genre-tags">{{ jam.genre_tags | join: " · " }}</p>
      {%- endif -%}
    </div>
  </li>
  {%- endfor -%}
</ul>
