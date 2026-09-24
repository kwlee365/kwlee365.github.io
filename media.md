---
layout: page
title: Media
subtitle: Press coverage and broadcast appearances.
permalink: /media/
---

{%- capture yearstr -%}{%- for m in site.data.media -%}{{ m.date | slice: 0, 4 }},{%- endfor -%}{%- endcapture -%}
{%- assign years = yearstr | split: "," | uniq -%}

{% for y in years %}
<h2 class="year-head">{{ y }}</h2>
<ul class="card-list">
  {%- for m in site.data.media -%}
  {%- assign my = m.date | slice: 0, 4 -%}
  {%- if my == y %}
  <li class="card">
    <p class="card-title">
      {%- if m.url != "" -%}
      <a href="{{ m.url | escape }}" target="_blank" rel="noopener">{{ m.title }}</a>
      {%- else -%}
      {{ m.title }}
      {%- endif -%}
    </p>
    <p class="card-sub">{{ m.outlet }} &middot; {{ m.date }}</p>
    <div class="pill-row">
      {%- if m.kind == 'video' %}
      <span class="pill"><i class="fab fa-youtube"></i> Video</span>
      {%- else %}
      <span class="pill"><i class="fas fa-newspaper"></i> Article</span>
      {%- endif %}
    </div>
  </li>
  {%- endif -%}
  {%- endfor %}
</ul>
{% endfor %}
