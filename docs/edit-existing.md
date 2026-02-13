---
title: Edit an existing guide
layout: page
nav_order: 4
description: Guide on editing the tutorials-search portal records
created_date: 2026-02-12
has_children: False
permalink: /edit-existing-guide/
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---

# Edit an existing guide

If you are editing an existing guide, you would need to clone (download) the GitHub repository to your local machine first.

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

# Next steps
After changing the content, you can preview the website. See this

## To preview the website

1. Run bundle install  to install the necessary files to start the preview server

    ```powershell
    bundle install
    ```

    <a href="{{ '/assets/images/05-bundle_install.gif' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/05-bundle_install.gif' | relative_url }}" 
        alt="Bundle Install in PowerShell"
        style="width:600px; display:block; margin:auto;">
    </a>

2. Run the following command to start the Jekyll server with live reload enabled

    ```powershell
    bundle exec jekyll serve --livereload
    ```

    <a href="{{ '/assets/images/06-bundle-exec.gif' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/06-bundle-exec.gif' | relative_url }}" 
        alt="Jekyll Serve in PowerShell"
        style="width:600px; display:block; margin:auto;">
    </a>

    Once you see the following message in the terminal, you may access the preview pages in your preferred web browser via http://127.0.0.1:4000 (or whatever address the terminal shows after the Server address line)

    ```text
    ...
    You can add fiddle to your Gemfile or gemspec to silence this warning.
    LiveReload address: http://127.0.0.1:35729
        Server address: http://127.0.0.1:4000
    Server running... press ctrl-c to stop.
    ```