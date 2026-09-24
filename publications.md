---
layout: page
title: Publications
subtitle: Papers on humanoid locomotion, whole-body control, and safety-critical control. My name is highlighted.
permalink: /publications/
---

{%- assign pubs = site.data.publications -%}
{%- assign years = pubs | map: "year" | uniq | sort | reverse -%}

{% for y in years %}
<h2>{{ y }}</h2>
<ol class="pub-list">
  {%- for pub in pubs -%}
  {%- if pub.year == y %}
  <li class="pub">
    <div class="pub-num">[{{ forloop.index }}]</div>
    <div>
      <div class="pub-title">{{ pub.title }}</div>
      <div class="pub-authors">{{ pub.authors | markdownify | remove: '<p>' | remove: '</p>' | replace: '<strong>', '<span class="me">' | replace: '</strong>', '</span>' }}</div>
      <div class="pub-venue">{{ pub.venue }}</div>
      <div class="pub-links">
        <span class="tag type">{{ pub.type }}</span>
        {%- for l in pub.links %}
        <a class="tag" href="{{ l.url }}" target="_blank" rel="noopener">{{ l.text }} <i class="fas fa-arrow-up-right-from-square" style="font-size:.7em"></i></a>
        {%- endfor %}
      </div>
    </div>
  </li>
  {%- endif -%}
  {%- endfor %}
</ol>
{% endfor %}

<p style="margin-top:2.5rem;font-size:.9rem;color:var(--text-muted)">
A full CV is available on request.
</p>
