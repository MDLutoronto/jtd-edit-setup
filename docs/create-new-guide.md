---
title: Create a New Guide
layout: page
nav_order: 3
description: Guide on creating a new Just-the-docs site with MDLutoronto template
created_date: 2025-12-09
has_children: False
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---
This guide will walk you through the steps to create a new guide with MDLutoronto's Just-the-docs template.

The <a href="https://github.com/MDLutoronto/jtd-template" target="_blank">MDLutoronto/jtd-template</a> repository is a template repository that contains the necessary structure and files to create a new Just-the-docs site.

## Creating a new repository
1. Click on the `Use this template` button at the top right of this repository page. Then, click on the `Create a new repository` button.

    <img src="{{ "/assets/images/create-new-guide/use-this-template.png" | relative_url}}" alt="Use this template button location" style="width:400px;"/>

2. You will be prompted to enter a repository name, description, and other settings.
   1. For the owner, choose `MDLutoronto`.
   2. Enter the name (also act as the slug) for your new Just-the-docs site.
   3. Enter a description for your new repository.
   4. Choose the repository visibility (public or private).

    {: .important }
    > Note that to make the site visible to everyone, you need to choose `public` as the repository visibility eventually.

    <img src="{{ "/assets/images/create-new-guide/create-a-new-repository.png" | relative_url}}" alt="Create a new repository form" style="width:400px;"/>

5. Click on the `Create repository` button on the bottom right to create your new repository.

    <img src="{{ '/assets/images/create-new-guide/create-repository.png' | relative_url}}" alt="Create repository button" style="width:200px;"/>
6. You will be prompted to the new repository page in a few seconds.

   <img src="{{ '/assets/images/create-new-guide/generating-your-repository.png' | relative_url}}" alt="Generating your new repository" style="width:200px;"/>

   <img src="{{ '/assets/images/create-new-guide/new-repo.png' | relative_url}}" alt="New repository page" style="width:600px;"/>

## Enabling GitHub Pages

1. You will first need to enable GitHub Pages. Go to the `Settings` tab of your new repository. Then, click on the `Pages` option in the left sidebar. Lastly, under `Source`, select 'GitHub Actions' from the dropdown menu.

   <img src="{{ '/assets/images/create-new-guide/github-pages-setting.png' | relative_url}}" alt="Repository settings tab" style="width:600px;"/>
## Modifying the configuration file

1. In order publish the website, you will have to modify the `_config.yml` file in your new repository, with the following modifications:
   1. First, replace the `jtd-theme` in the `url` field with the name of your new repository.
   
   For example, if your new repository is called `a-new-tutorial`, the `url` field should look like this:
   ```yaml
   url: "https://MDLutoronto.github.io/a-new-tutorial"
   ```
    
   2. Then, replace the repository: "MDLutoronto/jtd-theme" with the name of your new repository. For example, if your new repository is called `a-new-tutorial`, the `repository` field should look like this:
   ```yaml
   url: "MDLutoronto/a-new-tutorial"
   ```
      <img src="{{ '/assets/images/create-new-guide/change-config.png' | relative_url}}" alt="Change _config.yml" style="width:600px;"/>

   3. Commit the changes to the `_config.yml` file. Enter your commit message. Ensure the `Commit directly to the main branch` option is selected, then click on the `Commit changes` button.

      <img src="{{ '/assets/images/create-new-guide/commit-changes.png' | relative_url}}" alt="Commit changes to _config.yml" style="width:600px;"/>

You should now be able to see your new site at `https://MDLutoronto.github.io/your-repo-name` within a few minutes. For example, if your new repository is called `a-new-tutorial`, you should be able to see your new site at `https://MDLutoronto.github.io/a-new-tutorial`.

# Creating a new page
To create a new page in your Just-the-docs site, follow these steps:

1. In your new repository, navigate to the `docs` folder.
2. Create a new markdown file with the desired name for your new page. For example, if you want to create a page called `home`, create a file named `home.md`.
3. Add the necessary front matter to the top of the markdown file.
   ```yaml
   ---
   title: Home   # Title of the page, which will be displayed in the navigation and the browser title.
   layout: page  # Layout type, usually 'page' for standard pages.
   nav_order: 1  # Order in the navigation menu.
   description:  # A brief description of the page for SEO purposes.
   permalink: /  # Optional: Custom URL for the page. It will serve as the slug. For example, /home/
   created_date:  # Date when the page was created. Should be in YYYY-MM-DD format.
   has_children: False  # Set to True if the page has subpages.
   ---
   ```

4. Add the content for your new page below the front matter, for example:

   ```markdown
   ---
   title: Home   # Title of the page, which will be displayed in the navigation and the browser title.
   layout: page  # Layout type, usually 'page' for standard pages.
   nav_order: 1  # Order in the navigation menu.
   description:  # A brief description of the page for SEO purposes.
   permalink: /  # Optional: Custom URL for the page. It will serve as the slug. For example, /home/
   created_date:  # Date when the page was created. Should be in YYYY-MM-DD format.
   staff:  # Optional: Nested list of staff members associated with the page.
      - name: Staff One
        link: https://library.utoronto.ca/staff/staff-one  # link is optional
      - name: Another Staff
        link: https://example.com/another-staff
   student_staff:  
      - name: Student Name
        link: https://example.com/student-name
      - name: Another Student
        link: https://example.com/another-student  # link is optional
   has_children: False  # Set to True if the page has subpages.
   ---

   # Title of the Page
   Hello World! This is my new page.
   (content goes here)

   ```

   For the staff and student_staff fields, it is in a nested list format. Each staff member or student should have a `name` and an optional `link` field. See the <a href="https://yaml.org/spec/1.2.2/#Example%202.12%20Compact%20Nested%20Mapping:~:text=Example%202.12%20Compact%20Nested%20Mapping" target="_blank"> YAML documentation for Nested Lists</a> for more details


   See the <a href="{{ '/docs/sink/' | relative_url }}">Sink</a> guide for the UI elements you can use in your markdown files.