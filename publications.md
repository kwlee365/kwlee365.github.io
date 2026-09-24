---
layout: page
title: Publications
subtitle: Humanoid locomotion, whole-body control, and safety-critical control. My name is highlighted.
permalink: /publications/
---

{%- assign pubs = site.data.publications -%}
{%- assign years = pubs | map: "year" | uniq | sort | reverse -%}

{% for y in years %}
<h2 class="year-head">{{ y }}</h2>
<ul class="card-list">
  {%- for pub in pubs -%}
  {%- if pub.year == y %}
  <li class="card">
    <p class="card-title">{{ pub.title }}</p>
    <p class="card-sub">{{ pub.authors | markdownify | remove: '<p>' | remove: '</p>' | replace: '<strong>', '<span class="me">' | replace: '</strong>', '</span>' }}</p>
    <p class="card-venue">{{ pub.venue }}</p>
    <div class="pill-row">
      <span class="pill">{{ pub.type }}</span>
      {%- for l in pub.links %}
      <a class="pill" href="{{ l.url }}" target="_blank" rel="noopener"><i class="fas fa-link"></i> {{ l.text }}</a>
      {%- endfor %}
    </div>
  </li>
  {%- endif -%}
  {%- endfor %}
</ul>
{% endfor %}

<p style="font-size:.85rem;color:var(--text-muted)">A full CV is available on request.</p>
