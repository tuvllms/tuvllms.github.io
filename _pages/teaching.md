---
layout: page
title: teaching
permalink: /teaching/
description:
nav: true
nav_order: 5
display_categories: ['Spring 2025']
horizontal: false
---

<!-- pages/projects.md -->
<style>
/* Ensure a single card per row, spanning full width */
.projects .list {
    display: flex;
    flex-direction: column;
    gap: 20px; /* Space between cards */
}

.projects .list .project-card {
    width: 100%; /* Each card takes full width */
}
</style>

<div class="projects">
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
