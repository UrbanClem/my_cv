---
layout: pdf
title: CV - Alejandro Rodriguez
permalink: /cv-pdf/
---

# {{ site.title }}
## Software Engineering Student

{{ site.data.cv.description }}

{% for section in site.data.cv.sections %}
## {{ section.title }}

  {% for entry in section.entries %}
### {{ entry.title }}
  <div class="entry-header">
    {% if entry.sub %}<span class="entry-title">{{ entry.sub }}</span>{% endif %}
    <span class="entry-date">{{ entry.dates }}</span>
  </div>
  {% if entry.location %}
  <div class="entry-location">{{ entry.location }}</div>
  {% endif %}
  {% if entry.bullets %}
    {% if entry.bullets.first %}
<ul>
    {% for bullet in entry.bullets %}
    <li>{{ bullet }}</li>
    {% endfor %}
</ul>
    {% else %}
<p>{{ entry.bullets }}</p>
    {% endif %}
  {% endif %}
  {% endfor %}
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