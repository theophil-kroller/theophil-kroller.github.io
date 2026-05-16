---
layout: page
title: projects
description:
permalink: /projects/
nav: true
nav_order: 3
---

## Selected Projects

This page collects selected research, teaching, and innovation projects that connect my work in entrepreneurship education, management, sustainability, and applied learning.

### Doctoral Research: Technology Leadership in the Green Transition

My doctoral research focuses on technology leadership and followership strategies in the transition toward circular and regenerative economic systems. I am particularly interested in how greentech startups position themselves strategically in emerging technology fields and how they navigate uncertainty, innovation dynamics, and sustainability-oriented transformation.

**Status:** ongoing doctoral research  
**Fields:** technology leadership, circular economy, regenerative economy, greentech startups, qualitative research

### Unite! Seed Fund Project

This section is currently being expanded.

The Unite! Seed Fund project involves international collaboration with partners in Wrocław and focuses on [insert working title / topic]. The project connects research, teaching, and international cooperation around [insert theme].

**Status:** in development  
**Partners:** TU Graz and [partner institution in Wrocław]  
**Fields:** [insert fields]

### Business Model Lab: Sustainable Business Models

In the Business Model Lab, I contribute to a workshop format on sustainable business models for small and medium-sized enterprises. The format combines circular economy, sustainability, design thinking, sustainable business model patterns, prototyping, and the Flourishing Business Model Canvas.

The aim is to help participants move from broad sustainability challenges toward concrete business model ideas and prototypes that can be further developed in their organizational contexts.

**Status:** upcoming / in development  
**Fields:** sustainable business models, circular economy, design thinking, SME transformation

### Teaching Innovation in Entrepreneurship and Management Education

My teaching innovation work focuses on active learning formats in entrepreneurship and management education. Examples include role-card exercises, group puzzles, business model development games, market sizing worksheets, case-based organizational design exercises, and structured peer feedback formats.

**Status:** ongoing development  
**Fields:** entrepreneurship education, active learning, business model development, higher education didactics

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
