---
layout: page
title: teaching
permalink: /teaching/
description:
nav: true
nav_order: 5
display_categories: [work, fun]
horizontal: true
---

<!-- pages/projects.md -->

<div class="teaching">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  <div class="list">
    {%- for project in sorted_projects -%}
      <div class="project-card">
        {% include projects.html %}
      </div>
    {%- endfor %}
  </div>
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  <div class="list">
    {%- for project in sorted_projects -%}
      <div class="project-card">
        {% include projects.html %}
      </div>
    {%- endfor %}
  </div>
{%- endif -%}
</div>
