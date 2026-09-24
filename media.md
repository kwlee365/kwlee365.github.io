---
layout: page
title: Media
subtitle: Press coverage and broadcast appearances.
permalink: /media/
---

<ul class="card-list">
{%- for m in site.data.media %}
  <li class="card">
    <p class="card-title">
      {%- if m.url != "" -%}
      <a href="{{ m.url | escape }}" target="_blank" rel="noopener">{{ m.title }}</a>
      {%- else -%}
      {{ m.title }}
      {%- endif -%}
    </p>
    <p class="card-sub">{{ m.outlet }}{% if m.date %} &middot; {{ m.date }}{% endif %}</p>
    <div class="pill-row">
      {%- if m.kind == 'video' %}
      <span class="pill"><i class="fab fa-youtube"></i> Video</span>
      {%- else %}
      <span class="pill"><i class="fas fa-newspaper"></i> Article</span>
      {%- endif %}
    </div>
  </li>
{%- endfor %}
</ul>
