---
title: Rendering Tables from CSV (to interactive tables)
layout: wide
nav_order: 3
description: Guide on rendering tables from CSV files in Just-the-docs (with tabulator)
created_date: 2026-05-26
parmalink: /render-csv-tabulator/
parent: Markdown kitchen sink
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
maintainer: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---
# Table of Contents
{: .no_toc }
1. Table of Contents
{:toc}

{: .note }
This page uses a wide layout. This can be configured in the front matter of the page with `layout: wide`
<br><br>It is a recommended layout for displaying tables, especially tables with many columns.

# Data from CSV with Tabulator

This page demonstrates how to render interactive tables from CSV files using the [Tabulator library](https://tabulator.info/) in Just-the-docs.

The backend uses the Tabulator library with custom modifications (which the source code can be found in the `_includes/csv_table.html` in the MDLutoronto/jtd-theme _includes/csv_table.html).

The Tabulator library provides several powerful features for displaying CSV data:

- Pagination, sorting, and searching
- Efficient handling of large datasets
- Configurable table height and rows per page
- Default column sorting on load
- Automatic conversion of `http://` and `https://` URLs into clickable links


# Making the CSV Table Interactive with Tabulator

## Prerequisites

First, create a CSV file in the `/docs/_data` folder. For example, create `/docs/_data/another_data.csv` with your tabular data.

## Basic Usage

Use the following code to include the CSV table with Tabulator features. Replace `another_data` with the name of your CSV file (without the `.csv` extension):

```
{% raw %}{% include csv_table.html data_key="another_data" %}{% endraw %}
```

The table would look like as below:

***

{% include csv_table.html data_key="another_data"%}

***

## Parameters

These are the available options for the `csv_table` include:

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `data_key` | Yes | — | Filename of your CSV in `_data/` (without extension) |
| `table_id` | No | slugified `data_key` | HTML `id` for the table element |
| `pagination_size` | No | `50` | Rows per page |
| `height` | No | none | Fixed height (e.g. `"400px"`); omit for auto |
| `initial_sort_col` | No | none | Column name to sort by on load |
| `initial_sort_dir` | No | `"asc"` | Sort direction: `"asc"` or `"desc"` |

To use the parameters, place them within the `csv_table` include, and separate them with spaces. Example with all parameters:

```liquid
{% raw %}{% include csv_table.html data_key="another_data" table_id="my-table" pagination_size="20" height="400px" initial_sort_col="Name" initial_sort_dir="asc" %}{% endraw %}
```