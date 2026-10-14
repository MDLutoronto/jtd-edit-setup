---
title: Home
layout: home
nav_order: 1
description: Home page for Just-the-docs documentation for MDL JTD sites.
permalink: /
created_date: 2025-12-09
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
maintainer: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
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

# Introduction

Welcome to the Just-the-docs documentation home page for the Map & Data Library at the University of Toronto Libraries. Here you will find the guide on how to edit our just-the-docs based sites

# Structure of MDL just-the-docs sites

There are two main types of just-the-docs sites hosted by MDL via GitHub Pages:
1. **General guides sites**: These are the main how-to-guides for various topics, such as GIS, data visualization, etc. It is meant to be browsed by patrons, and was hosted on MDL Drupal site previously.
2. **Special sites**: These are just-the-docs sites that serve specific purposes, such as search portals, documentation for editing, etc.

## How the sites are related

```mermaid
flowchart TD
    accTitle: Relationships between the MDL just-the-docs sites
    accDescr: jtd-template is a GitHub template used to create each new guide. jtd-theme provides the look of the guides and this site. tutorials-search lists every guide. jtd-edit-setup documents how to edit all of them.
    theme["jtd-theme<br/>(remote theme)"]
    template["jtd-template<br/>(GitHub template)"]
    guides["General guide sites<br/>(one repository per guide)"]
    search["tutorials-search<br/>(search portal)"]
    editsetup["jtd-edit-setup<br/>(this site)"]

    template -- "Use this template<br/>(one-time copy)" --> guides
    theme -. "remote_theme<br/>(applied on every build)" .-> guides
    theme -. "remote_theme" .-> editsetup
    search -- "lists and links to<br/>(guides.yml)" --> guides
    guides -- "sidebar title links back to" --> search
    editsetup -- "documents how to edit" --> guides
```

- **jtd-theme** controls the layout, styles and components of the guide sites and this site. A change to the theme appears on those sites the next time each one is built.
- **jtd-template** is a GitHub template. A new guide is created from it with the `Use this template` button, which copies its files once. Later changes to the template do **not** reach existing guides. See [Breaking changes to _config.yml]({{ '/breaking-changes/' | relative_url }}) for the changes that existing guides need to apply by hand.
- **General guide sites** are created from the template and use the theme. Each guide has its own repository.
- **tutorials-search** is the entry point for patrons. It lists every guide from its `guides.yml` file, so it must be updated whenever a guide is created, renamed or removed. See [Edit the tutorials-search Records]({{ '/edit-tutorials-search/' | relative_url }}).
- **jtd-edit-setup** (this site) is the documentation for editing all of the above.

## Special sites

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