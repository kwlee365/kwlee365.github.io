---
layout: home
title: About
---

<h1>About me</h1>

<p class="lead">
I’m a <strong>Ph.D. candidate</strong> in the
<a href="https://gsai.snu.ac.kr/">Intelligence and Information</a> program at
<strong>Seoul National University</strong>, affiliated with the
<a href="https://dyros.snu.ac.kr/">Dynamic Robotic Systems Lab (DYROS)</a> at SNU
and the
<a href="https://sites.google.com/view/kist-arc/home/?pli=1&amp;authuser=0">Advanced Robot Control Lab (ARC)</a>
at KIST.
</p>

<p>
My research interests include humanoid locomotion and whole-body control,
safety-critical humanoid control, and reducing the sim-to-real gap for robust
real-world robot deployment.
</p>

<h1>Affiliations</h1>

<ul class="interests">
  {%- for a in site.data.affiliations %}
  <li>
    <span class="topic"><a href="{{ a.url }}" target="_blank" rel="noopener">{{ a.lab }}</a></span>
    &mdash; {{ a.org }}{% if a.note %}. {{ a.note }}{% endif %}
  </li>
  {%- endfor %}
</ul>

<h1>Research interests</h1>

<ul class="interests">
  {%- for item in site.data.interests %}
  <li>
    <span class="topic">{{ item.topic }}</span> —
    {{ item.detail }}{% if item.link %} (<a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.link_text | default: "link" }}</a>){% endif %}
  </li>
  {%- endfor %}
</ul>

<h1>News</h1>

<ul class="news">
  {%- for item in site.data.news %}
  <li>
    <span class="when">{{ item.when }}</span>
    <span>{{ item.what | markdownify | remove: '<p>' | remove: '</p>' }}</span>
  </li>
  {%- endfor %}
</ul>

<h1>Media</h1>

<ul class="media-list">
  {%- for m in site.data.media %}
  <li>
    <i class="{% if m.kind == 'video' %}fab fa-youtube{% else %}fas fa-newspaper{% endif %} kind"></i>
    <div>
      {%- if m.url != "" %}
      <a href="{{ m.url | escape }}" target="_blank" rel="noopener">{{ m.title }}</a>
      {%- else %}
      <span>{{ m.title }}</span>
      {%- endif %}
      <div class="outlet">{{ m.outlet }}{% if m.date %} &middot; {{ m.date }}{% endif %}</div>
    </div>
  </li>
  {%- endfor %}
</ul>

<h1>Education</h1>

<ul class="timeline">
  {%- for e in site.data.education %}
  <li>
    <div class="entry-head">
      <span class="entry-title">{{ e.school }}</span>
      <span class="entry-when">{{ e.when }}</span>
    </div>
    <div class="entry-meta">{{ e.degree }} &middot; {{ e.where }}</div>
    {%- if e.note %}<div class="entry-note">{{ e.note }}</div>{% endif %}
  </li>
  {%- endfor %}
</ul>

<h1>Teaching</h1>

<ul class="timeline">
  {%- for t in site.data.teaching %}
  <li>
    <div class="entry-head">
      <span class="entry-title">{{ t.role }}</span>
      <span class="entry-when">{{ t.when }}</span>
    </div>
    <div class="entry-meta">{{ t.org }}</div>
    <ul style="margin-top:.4rem;font-size:.92rem;">
      {%- for i in t.items %}<li>{{ i }}</li>{% endfor %}
    </ul>
  </li>
  {%- endfor %}
</ul>

<h1>Technical skills</h1>

<ul class="skills">
  {%- for s in site.data.skills %}
  <li><span class="k">{{ s.k }}</span>{{ s.v }}</li>
  {%- endfor %}
</ul>

<h1>Contact</h1>

<p>
Email <a href="mailto:{{ site.author.email }}">{{ site.author.email }}</a> —
happy to talk about humanoid control, motion retargeting, or safe RL.
A full CV is available on request.
</p>
