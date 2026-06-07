---
layout: pdf
title: CV - Tu Nombre
permalink: /cv-pdf/
---

# Tu Nombre Completo
## Software Engineering Student

{{ site.data.cv.description }}

{% for section in site.data.cv.sections %}
## {{ section.title }}

  {% for entry in section.entries %}
### {{ entry.title }}
{% if entry.sub %}*{{ entry.sub }}*{% endif %}
  <div class="entry-header">
    <span class="entry-title">{{ entry.title }}</span>
    <span class="entry-date">{{ entry.dates }}</span>
  </div>
  {% if entry.location %}
  <div class="entry-location">{{ entry.location }}</div>
  {% endif %}
  {% if entry.bullets %}
  <ul>
    {% for bullet in entry.bullets %}
    <li>{{ bullet }}</li>
    {% endfor %}
  </ul>
  {% endif %}
  {% endfor %}
{% endfor %}

## Technical Skills

{% for entry in site.data.cv.sections %}
  {% if entry.title == "Technical Skills" %}
    {% for skill in entry.entries %}
### {{ skill.title }}
      {% if skill.bullets %}
        {% if skill.bullets.first %}
<ul>
  {% for bullet in skill.bullets %}
  <li>{{ bullet }}</li>
  {% endfor %}
</ul>
        {% else %}
<p>{{ skill.bullets }}</p>
        {% endif %}
      {% endif %}
    {% endfor %}
  {% endif %}
{% endfor %}

## Projects

{% for project in site.data.projects.entries %}
### {{ project.title }}
<div class="entry-header">
  <span class="entry-title">{{ project.sub }}</span>
  <span class="entry-date">{{ project.dates }}</span>
</div>
<div class="entry-location">{{ project.location }}</div>
<ul>
  {% for bullet in project.bullets %}
  <li>{{ bullet }}</li>
  {% endfor %}
</ul>
{% endfor %}