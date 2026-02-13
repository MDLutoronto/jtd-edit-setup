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

## Clone the GitHub repository

{: .important }
> Here is a sandbox repository to test your access rights/connection:
>[MDLutoronto/just-the-docs-sandbox-stduents](https://github.com/MDLutoronto/just-the-docs-sandbox-students)
> After logging in with your account that has access to the MDL GitHub repository, you should be able to view the (private) repository in your web browser.

1. Open a (Windows) PowerShell Terminal
    <a href="{{ '/assets/images/01_powershell.gif' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/01_powershell.gif' | relative_url }}" 
        alt="Open PowerShell"
        style="width:600px; display:block; margin:auto;">
    </a>

2. Get the GitHub repository link to clone

    1. Go to the intended GitHub repository page in your web browser (e.g. [MDLutoronto/jtd-student-sandbox](https://github.com/MDLutoronto/jtd-student-sandbox))
    2. Click on the green `Code` button on the top right of the repository file list
    3. Make sure the `HTTPS` tab is selected, then click on the clipboard icon to copy the repository link
    <img src="{{ '/assets/images/get-repo-link.png' | relative_url }}" 
        alt="Get GitHub Repo Clone Link"
        style="width:500px; display:block; margin:auto;">

3. Type the command below in a powershell terminal to clone a GitHub repository. Replace the git_link with the intended GitHub repository link.

    ```powershell
    git clone $git_link
    ```

    For example, if you want to clone the sandbox repository above (with the .git link https://github.com/MDLutoronto/jtd-student-sandbox.git), you will input
    ```powershell 
    git clone https://github.com/MDLutoronto/jtd-student-sandbox.git
    ```

    {: .highlight-title }
    > Tip
    >
    > You can right-click on the terminal to paste the copied text to the terminal

    <a href="{{ '/assets/images/03_gh-clone.gif' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/03_gh-clone.gif' | relative_url }}" 
        alt="GitHub Repo Clone"
        style="width:600px; display:block; margin:auto;">
    </a>


## Enter the repository directory

1. Once you have cloned the repository, type `cd $directory_name` to *change the directory* (`cd`) of the terminal to the repository directory.
    
    The `directory_name` by default is the repository name (slug). As for the example above, it is `jtd-student-sandbox`

    {: .highlight-title }
    > Tip
    >
    > To utilize the auto-complete function (avoid typing the long string), type a few characters and press `Tab` to let the terminal finish it.

    <a href="{{ '/assets/images/04-cd_dir.gif' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/04-cd_dir.gif' | relative_url }}" 
        alt="Change Directory in PowerShell"
        style="width:600px; display:block; margin:auto;">
    </a>

    You should see the prompt in the terminal changed to PS H:\just-the-docs-sandbox-students> with the above example

2. Type `code .`  in the terminal to initialize the VS Code for this repository directory.

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