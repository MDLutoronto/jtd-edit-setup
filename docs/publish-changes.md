---
title: Publish the changes to GitHub
layout: page
nav_order: 4
description: Guide on publishing the changes to GitHub (Commit and Push)
created_date: 2026-02-12
has_children: False
parent: Preview website and publish the changes
permalink: /publish-changes/
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---

# Publish the changes to GitHub

It is important to understand the concepts of **commit** and **push** when working with just the docs sites.

## Commit and Push
### Commit
- Saves a snapshot of your changes (version of the files)
- Stored in your **local repository** (folder on your computer)
- Does **not** affect GitHub yet

### Push
- Uploads your committed changes to the **remote repository** (the cloud, e.g. GitHub)
- Makes changes visible to others
- Synchronizes local and remote repositories

{: .important-title }
> Summary
>
> To publish your changes, you first need to **commit**, then **push** the committed changes to the remote repository (GitHub).

## Steps to Commit and Push Changes
Assuming you are in the VS code terminal and finished editing the files.

1. Follow the steps below to **commit** the changes to your local repository:
    1. First, click the 'Source Control' icon on the left sidebar in VS Code. 
    2. Next click the '+' icon next to the files you want to commit (or click the '+' icon next to 'Changes' to stage all changes). 
    3. After that, enter a meaningful commit message that describes the changes you made in the 'Message' box and click the checkmark icon to commit the changes.

    <a href="{{ '/assets/images/publish-changes/stage-and-commit.gif' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/publish-changes/stage-and-commit.gif' | relative_url }}" 
        alt="Stage and Commit Changes in VS Code"
        style="width:600px; display:block; margin:auto;">
    </a>

2. After committing, you need to **push** the changes to GitHub:
    1. Click on the 'Graph' tab below the 'Changes' section in the Source Control panel.
    2. Then click the 'Push' button to upload your committed changes to GitHub. You should see the 'Ongoing changes..' message disappear once the push is successful.

    <a href="{{ '/assets/images/publish-changes/push-using-graph.gif' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/publish-changes/push-using-graph.gif' | relative_url }}" 
        alt="Push Changes in VS Code using the graph tab under Source Control"
        style="width:600px; display:block; margin:auto;">
    </a>  