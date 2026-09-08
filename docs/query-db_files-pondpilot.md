---
title: Query data files with PondPilot
layout: wide
nav_order: 4
description: Guide to creating live SQL query boxes with the PondPilot widget
created_date: 2026-05-26
permalink: /query-db-files-pondpilot/
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
This page uses the wide layout, which gives query results more room. Set `layout: wide` in the page's front matter to use it.

# Query a data file with PondPilot

<a href="https://pondpilot.io/widget/" target="_blank" rel="noopener noreferrer">PondPilot Widget</a> adds an interactive SQL editor to a page. It runs DuckDB-Wasm in the visitor's browser, so a query can read a data file published with your site and display the results without a server-side database. This is useful for creating live demos of SQL queries, or allowing visitors to explore a dataset.

## Supported file formats
According to the <a href="https://docs.pondpilot.io/pondpilot/getting-started/#loading-your-first-data" target="_blank" rel="noopener noreferrer">PondPilot Documentation</a>, the following file formats are supported:
1. CSV/TSV - Comma or tab-separated values
2. JSON - JSON arrays or newline-delimited JSON
3. Parquet - Apache Parquet files
4. XLSX - Excel spreadsheets (each sheet becomes a table)
5. DuckDB - DuckDB database files

## Add the PondPilot widget

PondPilot supports both querying a local file and querying a file hosted on another site. 

### Query a local file

First, create a data folder under `docs/assets`, then place your file in it. For example:

```text
docs/
└── assets/
    └── data/
        └── orders.parquet
```

{: .warning }
Anything stored in `docs/assets` is publicly accessible after the site is published. Do not place private or sensitive data there.

Add the widget script and a SQL query to the Markdown page where the query box should appear:

```html
{% raw %}<script src="https://unpkg.com/pondpilot-widget@1.4.0"></script>

<pre class="pondpilot-snippet">
SELECT *
FROM '{{ site.baseurl }}/assets/data/orders.parquet'
LIMIT 10;
</pre>{% endraw %}
```

Replace `orders.parquet` with the name of your file, and change the SQL query as needed. Keep `{% raw %}{{ site.baseurl }}{% endraw %}` in the path so the URL also works when the site is hosted below a domain subpath.

The `<pre class="pondpilot-snippet">` element must contain a complete SQL statement. An incomplete `FROM` clause will not work. Make sure every Liquid expression also has both its opening and closing braces.

However, when querying, you don't need to add the `{% raw %}{{ site.baseurl }}{% endraw %}` prefix to the file path to make it query a local file. For example:

```sql
SELECT O_ORDERKEY -- Or any other column
FROM '/assets/data/orders.parquet'
LIMIT 10;
```

### Query a file hosted on another site
A full URL can be used to query a file hosted on another site, for example:

```sql
SELECT *
FROM 'https://duckdb.org/data/cli/pop.csv'  -- or any other publicly accessible file
LIMIT 10;
```


## Test the query
Open the local site, visit the page containing the widget, and run the query. If the file cannot be loaded, check that:

- The file is under `docs/assets/data`, not `docs/_data`.
- The filename and capitalization in the query match the file exactly.
- The query uses {% raw %}`{{ site.baseurl }}/assets/data/...`{% endraw %}, or the full URL to the file.
- The file is present at `/assets/data/orders.parquet` on the locally served site.


## Live demo
The below is a live demo of the PondPilot widget. You can run the query and see the results below. The parquet file used in this demo is placed under `docs/assets/data/orders.parquet` in this repository. 

<script src="https://unpkg.com/pondpilot-widget@1.4.0"></script>

<pre class="pondpilot-snippet">
SELECT *
FROM '{{ site.baseurl }}/assets/data/orders.parquet'
LIMIT 10;
</pre>
