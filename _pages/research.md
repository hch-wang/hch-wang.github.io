---
layout: page
title: projects
permalink: /projects/
description: Selected research projects and explanatory notes, organized for readers who want a quick way into the underlying ideas.
nav: true
nav_order: 3
display_categories: ["Mathematical Physics", "Computer Science", "Other"]
horizontal: false
toc:
  sidebar: right
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <div class="tag-category-list project-area-list">
    <ul>
      {% for category in page.display_categories %}
        {% assign categorized_projects = site.projects | where: "category", category %}
        {% if categorized_projects.size > 0 %}
          <li>
            <i class="fa-solid fa-tag fa-sm"></i>
            <a href="#{{ category | slugify }}">{{ category }}</a>
          </li>
        {% endif %}
      {% endfor %}
    </ul>
  </div>

  <!-- Display categorized projects -->

{% for category in page.display_categories %}
{% assign categorized_projects = site.projects | where: "category", category %}
{% if categorized_projects.size > 0 %}

  <h2 id="{{ category | slugify }}" class="category" data-toc-text="{{ category }}">{{ category }}</h2>
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
