---
layout: home
title: About
---

<h1>About me</h1>

<p class="lead">
I am a <strong>Ph.D. course</strong> student in the
<a href="https://gsai.snu.ac.kr/">Intelligence and Information</a> program at
<strong>Seoul National University</strong>. I work in the
<a href="https://dyros.snu.ac.kr/">Dynamic Robotic Systems Lab (DYROS)</a> at SNU
and the
<a href="https://sites.google.com/view/kist-arc/home/?pli=1&amp;authuser=0">Advanced Robot Control Lab (ARC)</a>
at KIST.
</p>

<p>
My research is about making humanoid robots move <span class="hl">reliably</span> and
<span class="hl">safely</span> in the real world. I work across the whole stack that this
requires: model-based whole-body control and model predictive control for locomotion and
balance, control barrier functions that turn safety requirements into hard constraints, and
reinforcement learning policies trained on human motion that has been retargeted to be
kinematically and dynamically feasible on the robot.
</p>

<p>
Most of this work ends up running on real hardware — most recently on the humanoid platform
we demonstrated at <a href="https://www.youtube.com/watch?v=VUrm83OZvyA">CES 2026</a>.
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
