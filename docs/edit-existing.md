---
title: Edit a Guide
layout: page
nav_order: 4
description: Guide on editing the tutorials-search portal records
created_date: 2026-02-12
has_children: False
permalink: /edit-guide/
parent: Edit, Preview and Publish
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---

# Edit a Guide

If you have created a new guide or want to make changes to an existing guide, you can follow the instructions below.

To edit a guide, you will first need to clone (download) the GitHub repository to your local machine.

## Clone the GitHub repository in VS code

{: .important }
> Here is a sandbox repository to test your access rights/connection:
>[MDLutoronto/jtd-student-sandbox](https://github.com/MDLutoronto/jtd-student-sandbox).
> After logging in with your account that has access to the MDL GitHub repository, you should be able to view the (private) repository in your web browser.

1. Open VS Code, then click on the 'Source Control' icon on the left sidebar (or press Ctrl+Shift+G) to open the Source Control panel. Next, click on the 'Clone Repository' button. You should then see a prompt at the top of the window showing 'Clone from GitHub'. Click on it.

    <a href="{{ '/assets/images/clone-from-vscode/source-control-clone.png' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/clone-from-vscode/source-control-clone.png' | relative_url }}" 
        alt="Clone Repository in VS Code"
        style="width:600px; display:block; margin:auto;">
    </a>

2. A drop-down menu will appear, showing the repositories you have access to. Select or type the name of the repository you want to clone (i.e. download) to your local machine.

    <a href="{{ '/assets/images/clone-from-vscode/list-of-repos.png' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/clone-from-vscode/list-of-repos.png' | relative_url }}" 
        alt="List of repositories in VS Code"
        style="width:600px; display:block; margin:auto;">
    </a>
    The format of repository name of MDL GitHub  is `MDLutoronto/${repository-name}`. For example, the sandbox repository is `MDLutoronto/jtd-student-sandbox`.

3. Once you select the repository, you will be prompted to choose a local directory to save the cloned repository. Choose a location on your computer where you want to store the project files, then click 'Select as Repository Location'. You will see a message in the bottom right corner of the VS Code window saying 'Cloning git repository...'.
    <a href="{{ '/assets/images/clone-from-vscode/cloning-git-repo.png' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/clone-from-vscode/cloning-git-repo.png' | relative_url }}" 
        alt="Cloning Git repository in VS Code"
        style="width:300px; display:block; margin:auto;">
    </a>

4. After the cloning process is complete, you will see a message in the middle asking if you want to open the cloned repository. Click 'Open' to open the repository in VS Code.

    <a href="{{ '/assets/images/clone-from-vscode/open-repo.png' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/clone-from-vscode/open-repo.png' | relative_url }}" 
        alt="'Would you like to open the cloned repository?' prompt in VS Code"
        style="width:300px; display:block; margin:auto;">
    </a>

5. You should see the repository name in the left sidebar of VS Code (as the same as the local folder name). You can click on the 'Explorer' icon, then choose 'index.md' under docs to view the content of the guide in markdown format. You can edit the content in this file to make changes to the guide.

    <a href="{{ '/assets/images/clone-from-vscode/open-index_md.png' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/clone-from-vscode/open-index_md.png' | relative_url }}" 
        alt="Open index.md file in VS Code"
        style="width:600px; display:block; margin:auto;">
    </a>

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


   See the <a href="{{ '/sink/' | relative_url }}">Markdown Kitchen sink</a> page for the UI elements you can use in your markdown files.

# Next steps
After changing the content, you can preview the website. See the [Preview the website]({{site.baseurl}}/preview-website/) guide for instructions on how to do that. 

If you are ready to publish the changes, see the [Publish the guide]({{site.baseurl}}/publish-changes/) guide for instructions.