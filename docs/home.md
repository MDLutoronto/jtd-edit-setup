---
title: Home
layout: home
nav_order: 1
description: Home page for Just-the-docs documentation for MDL JTD sites.
permalink: /
created_date: 2025-12-09
staff_name: Ken Lui
staff_link: https://library.utoronto.ca/staff/ken-lui
---
<style>
  table {
    width: 100%;
    border-collapse: collapse;
  }
  
  table th, table td {
    word-wrap: break-word;
    word-break: break-word;
    overflow-wrap: break-word;
    padding: 12px;
    text-align: left;
    border: 1px solid #ddd;
  }
  
  table th {
    background-color: #f5f5f5;
    font-weight: bold;
  }
</style>

Welcome to the Just-the-docs documentation home page for the Map & Data Library at the University of Toronto Libraries. Here you will find the guide on how to edit our just-the-docs based sites

# Structure of MDL just-the-docs sites

There are two main types of just-the-docs sites hosted by MDL via GitHub Pages:
1. **General guides sites**: These are the main how-to-guides for various topics, such as GIS, data visualization, etc. It is meant to be browsed by patrons, and was hosted on MDL Drupal site previously.
2. **Special sites**: These are just-the-docs sites that serve specific purposes, such as search portals, documentation for editing, etc.

## Special sites:

{% assign special-sites = site.data.special-sites %}
<table>
  <thead>
    <tr>
      {% for header in special-sites.first %}
        <th>{{ header[0] }}</th>
      {% endfor %}
    </tr>
  </thead>
  <tbody>
    {% for row in special-sites %}
      <tr>
        {% for cell in row %}
          {% if cell[1] contains 'http' or cell[1] contains 'github' %}
            <td><a href="{{ cell[1] }}" target="_blank">{{ cell[1] }}</a></td>
          {% else %}
            <td>{{ cell[1] }}</td>
          {% endif %}
        {% endfor %}
      </tr>
    {% endfor %}
  </tbody>
</table>