---
layout: page
title: Notes
subtitle: Paper reviews, derivations, and implementation notes on humanoid control.
permalink: /notes/
---

{% if site.posts.size > 0 %}
<ul class="note-list">
  {%- for post in site.posts %}
  <li>
    <div class="when">{{ post.date | date: "%Y.%m.%d" }}</div>
    <div class="title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></div>
    {%- if post.excerpt %}<div style="font-size:.92rem;color:var(--text-muted)">{{ post.excerpt | strip_html | truncate: 160 }}</div>{% endif %}
  </li>
  {%- endfor %}
</ul>
{% else %}
<p class="empty">No notes published yet.</p>
{% endif %}
