---
title: Breaking changes to _config.yml
layout: page
nav_order: 8
description: A log of changes to the jtd-template _config.yml file that require updating existing guides
created_date: 2026-10-14
has_children: False
permalink: /breaking-changes/
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
maintainer: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---
# Introduction

Every guide is created from a copy of the <a href="https://github.com/MDLutoronto/jtd-template" target="_blank">MDLutoronto/jtd-template</a> repository. Once a guide is created, it does **not** receive later updates to the template's `_config.yml` file. 

This page lists the template changes that affect guides created **before** the change.

# Breaking changes

## 2026-10-14: Repository slug moved from `url` to `baseurl`

**Template commit:** <a href="https://github.com/MDLutoronto/jtd-template/commit/b9f5790" target="_blank">b9f5790</a>

### What changed

The repository name used to be part of the `url` field, and `baseurl` was left empty. The repository name now goes in the `baseurl` field, and `url` holds only the domain. The `url` field has moved into the 🚨 DANGER ZONE 🚨 section, since it is the same for every guide.

Before:
```yaml
## Site settings
url: "https://MDLutoronto.github.io/a-new-tutorial" # change the slug to the repo's name
...
# 🚨 DANGER ZONE 🚨
baseurl: "" # the subpath of your site, e.g. /blog
```

After:
```yaml
## Site settings
baseurl: "/a-new-tutorial" # Replace it with the "/" + repo's name (e.g. "/my-repo-name')
...
# 🚨 DANGER ZONE 🚨
url: "https://mdlutoronto.github.io"
```

# Adding a new entry

When you change the template's `_config.yml` in a way that breaks existing guides, add a new entry at the top of [Breaking changes](#breaking-changes) with:

- the date and a short title,
- a link to the template commit,
- a before and after example.