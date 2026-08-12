---
layout: page
permalink: /people/
title: People
description: Members of SRLab
nav: true
nav_order: 6
---

<div class="team">

<h2>Principal Investigator</h2>
{% assign pi = site.data.team.principal_investigator %}
<div class="team-list">
  <div class="team-row">
    {% if pi.image %}
    <img src="{{ '/assets/img/' | append: pi.image | relative_url }}" alt="{{ pi.name }}" class="team-photo">
    {% endif %}
    <div class="team-info">
      <a href="{{ pi.link }}"><strong>{{ pi.name }}</strong></a><br>
      {{ pi.title }}, {{ pi.affiliation }}
    </div>
  </div>
</div>

{% if site.data.team.members and site.data.team.members.size > 0 %}
<h2>Team Members</h2>
<div class="team-list">
  {% for member in site.data.team.members %}
  <div class="team-row">
    {% if member.image %}
    <img src="{{ '/assets/img/' | append: member.image | relative_url }}" alt="{{ member.name }}" class="team-photo">
    {% endif %}
    <div class="team-info">
      <a href="{{ member.link }}"><strong>{{ member.name }}</strong></a><br>
      {{ member.title }}, {{ member.affiliation }}, {{ member.project_title }}
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}


<h2>Collaborators</h2>
<ul>
  {% for collaborator in site.data.team.collaborators %}
  <li>
    <a href="{{ collaborator.link }}">{{ collaborator.name }}</a> — {{ collaborator.title }}, {{ collaborator.affiliation }}
  </li>
  {% endfor %}
</ul>

</div>

<style>
.team-list {
  margin-bottom: 20px;
}
.team-row {
  display: flex;
  align-items: center;
  gap: 15px;
  padding: 10px 0;
  border-bottom: 1px solid var(--global-divider-color);
}
.team-photo {
  width: 60px;
  height: 60px;
  object-fit: cover;
  border-radius: 50%;
  flex-shrink: 0;
}
.team-info {
  line-height: 1.4;
}
</style>
