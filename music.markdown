---
layout: page
title: Music
permalink: /music/
---

<style>
  .music-item {
    align-items: center;
    gap: 0.75rem;
  }

  .music-cover {
    width: 96px;
    height: 96px;
    object-fit: cover;
    border: 2px solid #000;
    flex-shrink: 0;
  }

  .music-info {
    display: flex;
    flex-direction: column;
    min-width: 0;
  }

  .music-title {
    color: #000;
  }

  .music-artist {
    color: #000;
  }

  .music-date {
    color: #4a4a4a;
    font-size: 0.85em;
    margin-top: 0.2rem;
  }

  .music-play {
    display: inline-block;
    flex-shrink: 0;
    margin-left: auto;
    color: #000;
    text-decoration: none;
    font-size: 1.6em;
    line-height: 1;
  }

  .music-play:hover {
    opacity: 0.6;
  }
</style>

<ul class="entry-list">
  {%- for jam in site.data.music -%}
  <li class="field-row music-item">
    {%- if jam.album_cover_url -%}
    <img class="music-cover" src="{{ jam.album_cover_url }}" alt="{{ jam.title | escape }} cover art">
    {%- endif -%}
    <div class="music-info">
      <span class="music-title">{{ jam.title }}{% if jam.artist %} - <span class="music-artist">{{ jam.artist }}</span>{% endif %}</span>
      {%- if jam.post_date -%}
      <span class="music-date">{{ jam.date | date: "%b %-d, %Y" }}</span>
      {%- endif -%}
      {%- if jam.description -%}
      <p class="entry-blurb">{{ jam.description }}</p>
      {%- endif -%}
      {%- if jam.genre_tags -%}
      <p class="genre-tags">{{ jam.genre_tags | join: " · " }}</p>
      {%- endif -%}
    </div>
    <a class="music-play" href="{{ jam.youtube_url }}" target="_blank" rel="noopener noreferrer" aria-label="Watch on YouTube">&#9654;</a>
  </li>
  {%- endfor -%}
</ul>
