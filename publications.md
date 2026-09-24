---
layout: page
title: Publications
subtitle: Grouped by type, then by year. My name is highlighted.
permalink: /publications/
---

{%- assign types = "Journal,Conference,Preprint" | split: "," -%}

{% for t in types %}
{%- assign items = site.data.publications | where: "type", t -%}
{%- if items.size > 0 %}
<h2 class="type-head">{{ t }}{% if items.size > 1 %}s{% endif %}</h2>

{%- assign years = items | map: "year" | uniq | sort | reverse -%}
{% for y in years %}
<h3 class="year-head">{{ y }}</h3>
<ul class="card-list">
  {%- for pub in items -%}
  {%- if pub.year == y %}
  <li class="card">
    <p class="card-title">
      {%- if pub.url -%}
      <a href="{{ pub.url | escape }}" target="_blank" rel="noopener">{{ pub.title }}</a>
      {%- else -%}
      {{ pub.title }}
      {%- endif -%}
    </p>
    <p class="card-sub">{{ pub.authors | markdownify | remove: '<p>' | remove: '</p>' | replace: '<strong>', '<span class="me">' | replace: '</strong>', '</span>' }}</p>
    <p class="card-venue">{{ pub.venue }}</p>
    {%- if pub.links %}
    <div class="pill-row">
      {%- for l in pub.links %}
      <a class="pill" href="{{ l.url | escape }}" target="_blank" rel="noopener"><i class="fas fa-link"></i> {{ l.text }}</a>
      {%- endfor %}
      {%- if pub.video %}
      <span class="pill plain"><i class="fab fa-youtube"></i> Video below</span>
      {%- endif %}
    </div>
    {%- endif %}
    {%- if pub.video %}
    <div class="video" data-yt="{{ pub.video }}" data-start="{{ pub.video_start | default: 0 }}" role="button" tabindex="0"
         aria-label="Play the video for {{ pub.title | strip | escape }}">
      <img src="https://i.ytimg.com/vi/{{ pub.video }}/hqdefault.jpg" alt="" loading="lazy" decoding="async">
      <span class="video-play"><i class="fas fa-play"></i></span>
    </div>
    {%- endif %}
  </li>
  {%- endif -%}
  {%- endfor %}
</ul>
{% endfor %}
{%- endif -%}
{% endfor %}

<p style="font-size:.85rem;color:var(--text-muted)">
Also on <a href="{{ site.author.scholar | escape }}" target="_blank" rel="noopener">Google Scholar</a>.
A full CV is available on request.
</p>
