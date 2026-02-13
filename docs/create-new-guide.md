---
title: Create a new guide on GitHub
layout: page
nav_order: 4
description: Guide on creating a new Just-the-docs site with MDLutoronto template
created_date: 2025-12-09
has_children: False
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---
# Introduction
This guide will walk you through the steps to create a new guide with MDLutoronto's Just-the-docs template.

The <a href="https://github.com/MDLutoronto/jtd-template" target="_blank">MDLutoronto/jtd-template</a> repository is a template repository that contains the necessary structure and files to create a new Just-the-docs site.

To create a new guide, you will first need to create a new repository using the template repository above.

# Steps
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

1. You will need to enable GitHub Pages to make the website visible. Go to the `Settings` tab of your new repository. Then, click on the `Pages` option in the left sidebar. Lastly, under `Source`, select 'GitHub Actions' from the dropdown menu.

   <img src="{{ '/assets/images/create-new-guide/github-pages-setting.png' | relative_url}}" alt="Repository settings tab" style="width:600px;"/>

   If it is already set, you can leave it as is and do not need to change it.

## Modifying the configuration file

1. In order publish the website, you will have to modify the `_config.yml` file in your new repository, with the following modifications:
   1. To modify the `_config.yml` file, click on the file in the repository file list. Then, click on the pencil icon on the top right corner of the file view to edit the file.

      
   2. First, replace the `jtd-theme` in the `url` field with the name of your new repository.
   
   For example, if your new repository is called `a-new-tutorial`, the `url` field should look like this:
   ```yaml
   url: "https://MDLutoronto.github.io/a-new-tutorial"
   ```
    
   3. Then, replace the repository: "MDLutoronto/jtd-theme" with the name of your new repository. For example, if your new repository is called `a-new-tutorial`, the `repository` field should look like this:
   ```yaml
   url: "MDLutoronto/a-new-tutorial"
   ```
      <img src="{{ '/assets/images/create-new-guide/change-config.png' | relative_url}}" alt="Change _config.yml" style="width:600px;"/>

   4. Change the title and description fields accordingly to the reflect the content of your new site. 

   5. Commit the changes to the `_config.yml` file. Enter your commit message. Ensure the `Commit directly to the main branch` option is selected, then click on the `Commit changes` button.

      <img src="{{ '/assets/images/create-new-guide/commit-changes.png' | relative_url}}" alt="Commit changes to _config.yml" style="width:600px;"/>

You should now be able to see your new site at `https://MDLutoronto.github.io/your-repo-name` within a few minutes. For example, if your new repository is called `a-new-tutorial`, you should be able to see your new site at `https://MDLutoronto.github.io/a-new-tutorial`.

## Next steps
To edit the content of your new guide, you can follow the guides in the [Edit, Preview and Publish]({{site.baseurl}}/edit-preview-and-publish/) section to learn how to edit the content, preview the changes locally, and publish the changes to GitHub.