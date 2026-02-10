---
title: Edit the migrated guides
layout: page
nav_order: 4
description: Guide on editing the migrated guides
created_date: 2026-01-21
has_children: False
permalink: /edit-migration-guides/
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---

# Introduction
This guide is for editing the migrated guides from MDL's Drupal site to Just-the-Docs sites.

Each guide was scrapped in HTML format using python, and later converted to markdown, and uploaded to the GitHub repositories. Each repository corresponds to a guide.


# Editing workflow

The workflow for editing the migrated guides is similar to editing any Just-the-Docs site. You can follow the steps below:

## Pre-requisites

1. Access the [tracking spreadsheet](https://utoronto.sharepoint.com/:x:/r/sites/utl-mdlstaff/Shared%20Documents/Student%20space/Projects/Website%20Migration%20to%20Just%20the%20docs/migration_progress_final.xlsx?d=wd45d233b9f5547aa9a50cce4ef58549a&csf=1&web=1&e=PMEclE) for this migration project. Claim one guides to edit.

2. Clone the repository of the guide you want to edit to your local machine. Check the [Setup for Editing Just-the-Docs Sites]({{site.baseurl}}/setup) guide for the prerequisite software and accounts.

3. Navigate to the directory where you cloned the repository. 

    Then, switch to the designated `initial-edit` branch, using the command:
      ```powershell
      git checkout initial-edit
      ```  

    Another way is to switch using the VScode feature. Open the Source Control pane, click on the branch name at the bottom left corner, and select `origin/initial-edit` from the list of branches. The VScode will automatically switch to the `initial-edit` branch.

4. Open the repository in your code editor (e.g., VScode), if you haven't done so.

5. Open the docs/index.md file. This is the main file to edit.

You are now ready to edit the docs. The editing steps can be divided into updating and checking.

## Updating the content

There are several things to update (add) in the migrated guides:

1. Front matter: Update the front matter at the top of the file. 

    - Update the `staff` section with the name and the link of the creator of the guide. If you see a active staff member, put their name and profile
      
      ```yaml
        staff:
          - name: Ken Lui
            link: https://library.utoronto.ca/staff/ken-lui
      ```
    
      For student staff member:
      
      ```yaml
        student_staff:
          - name: [Your Full Name]
            link: [Link to your profile page, e.g., UTL staff page]
      ```

      {: .note }
      If you notice the author is student staff, please add this to the 'issue' of the repository, and inform the supervising staff member to confirm which author name to put. 

    - Update the description section (plain text only, without markdown/html syntax, for example embedded links). Find the description in the [tutorial-search](https://mdlutoronto.github.io/tutorials-search/) site with the same guide title.
    
      You may also refer to the backend <a href="https://github.com/MDLutoronto/tutorials-search/blob/main/_data/guides.yml" target="_blank">YAML file</a>.

        ```yaml
          description: Guide on editing the migrated guides
        ```

    - At the bottom of the file, you might find the 'Date Created' value in the front matter. Update it to the current date in the format of `YYYY-MM-DD`. Delete hte 'Date Created' line, including the 'Updated:YYY-MM-DD' line, once you have updated it.

        ```yaml
          created_date: 2026-01-21
        ```

2. Update the syntax highlighting for code blocks. Make sure each code block has the correct language identifier after the triple backticks. You can check the <a href ='https://github.com/rouge-ruby/rouge/wiki/list-of-supported-languages-and-lexers' >rouge list for all the supported languages</a>. For example, for python code blocks, it should be:

    ```python
    # Your python code here
    def hello_world():
        print("Hello, world!")
    ```


## Checking the content

Check the following items while editing:

  1. **Ordered list**: rendered correctly and not with escaped characters (e.g. `1\.`)?
  2. **Embedded links** (out links): working correctly/not broken?
  3. **Anchor links** (internal links): working correctly/not broken?
  4. **Images**: rendered correctly/not broken?
  5. **Spacing issue**: extra or missing spaces between words or lines?

Once you have completed editing the guide, put a `Y` in the tracking spreadsheet's `initial_edit_status` column for the guide you edited.

## Another issues
If you notice any issue, please open a new 'issue' in the respective repository, and inform the supervising staff member. 

You can find the 'issue' tab in the repository, as shown in the image below:

<img src="{{ '/assets/images/issues.png' | relative_url }}" alt="Open issues" style="width:1200px;"/>

Give a clear title and description for the issue, and inform the supervising staff member to check and confirm the issue.

For example, if you notice the author of the guide is a student staff member, please mark it in the 'issue' and inform the supervising staff member to confirm which author name to put in the front matter.