---
title: Remove a guide from MDL GitHub
layout: page
nav_order: 6
description: Guide for deleting an existing tutorial
created_date: 2026-06-24
has_children: False
staff: 
   - name: Neil Aitken
     link: https://library.utoronto.ca/staff/neil-aitken
maintainer: 
   - name: Neil Aitken
     link: https://library.utoronto.ca/staff/neil-aitken
---
# Introduction
This guide will walk you through the steps to remove a guide from Tutorial Search and delete it from MDL's GitHub

# Steps
## Archiving a GitHub Repository
1. Using the command line, install *git2pdf* (git2pdf is a command-line tool for transforming GitHub repositories into PDF files)
  ```
  npm install -g git2pdf
  ```
2. Run git2pdf (change *tutorial-repo-name* to the tutorial's GitHub short name)
  ```
  git2pdf https://github.com/MDLutoronto/tutorial-repo-name --keep-repo  
  ```
3. Rename the output.pdf to the repository's name
4. Create a zip archive containing both the temp-repo folder and the pdf.
5. Rename the file to the repository short name and upload it to the MDL Sharepoint in the \Staff space\Archived GitHub Repositories folder

## Removing the Guide from Tutorial Search
1. To remove the guide from the main tutorial search page, you will have to modify the 'guides.yml' file (located at https://github.com/MDLutoronto/tutorials-search/blob/main/_data/guides.yml)
2. Search for the repository short name (or the GitHub repository's URL).
  1. If you find an entry with a matching URL, delete everything related to the entry (from id to type). See the example below:
     ```- id: 18
         title: "Bits and Bytes Series: Using LiDAR Data in ArcGIS Pro (Feb. 25, 2021)"
         url: https://mdlutoronto.github.io/bits-bytes-series-lidar-data-arcgis-feb-25-2021/
         description: |
          This page provides a presentation on **Using LiDAR Data in ArcGIS Pro** as part of the Bits and Bytes Webinar Series hosted by the Map & Data Library that features presentations and demonstrations on data-related topics and tools, such as web archives, visualization, GIS and statistics.
         technique:
          - Mapping
        tool:
          - ArcGIS Pro
        date: "2025-02-13"
        series: Bits and Bytes
        type: Video
     ```
  2. If there are no hits, someone else has already removed the entry.

