---
layout: page
title: Projects
subtitle: Funded research projects I have contributed to, most recent first.
permalink: /projects/
---

<ul class="card-list">
{%- for p in site.data.projects %}
  <li class="card">
    <div class="entry-head">
      <p class="card-title">{{ p.title }}</p>
      <span class="entry-when">{{ p.when }}</span>
    </div>
    {%- if p.title_ko %}<p class="card-sub">{{ p.title_ko }}</p>{% endif %}
    <p class="card-sub"><i class="fas fa-building-columns"></i> {{ p.funder }}</p>
    <ul>
      {%- for i in p.items %}<li>{{ i }}</li>{% endfor %}
    </ul>
    {%- if p.links %}
    <div class="pill-row">
      {%- for l in p.links %}
      <a class="pill" href="{{ l.url }}" target="_blank" rel="noopener"><i class="fab fa-youtube"></i> {{ l.text }}</a>
      {%- endfor %}
    </div>
    {%- endif %}
  </li>
{%- endfor %}
</ul>
