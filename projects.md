---
layout: page
title: Projects
subtitle: Funded research projects I have contributed to, most recent first.
permalink: /projects/
---

{% for p in site.data.projects %}
<div class="project">
  <div class="entry-head">
    <span class="project-title">{{ p.title }}</span>
    <span class="entry-when">{{ p.when }}</span>
  </div>
  {%- if p.title_ko %}<div class="project-funder">{{ p.title_ko }}</div>{% endif %}
  <div class="project-funder"><i class="fas fa-building-columns" style="font-size:.85em"></i> {{ p.funder }}</div>
  <ul>
    {%- for i in p.items %}<li>{{ i }}</li>{% endfor %}
  </ul>
  {%- if p.links %}
  <div class="pub-links" style="margin-top:.6rem">
    {%- for l in p.links %}
    <a class="tag" href="{{ l.url }}" target="_blank" rel="noopener"><i class="fab fa-youtube" style="font-size:.85em"></i> {{ l.text }}</a>
    {%- endfor %}
  </div>
  {%- endif %}
</div>
{% endfor %}
