---
title: Editing the tutorials-search Records
layout: page
nav_order: 1
description: 
permalink: /
created_date: 2025-12-05
# last_modified_date: # Only use it when you want to override the auto-updated date.
has_children: true
staff_name: Ken Lui
staff_link: https://library.utoronto.ca/staff/ken-lui
---

This tutorial will guide you on how to add or modify records in the [tutorials-search](https://github.com/MDLutoronto/tutorials-search) repository.

# Prerequisite
Follow the Home page's setup for the prerequisite software and accounts.

# Steps to Edit Records in tutorials-search
Background: The website is backed by a [guides.yml file](https://github.com/MDLutoronto/tutorials-search/blob/main/_data/guides.yml). Each record in the YAML file represents a tutorial record in the search site.

There are two ways to edit the records in the tutorials-search repository:
1. Clone the repository to your local machine, edit the `guides.yml` file using a text editor (e.g. VS Code), and push the changes back to GitHub.
2. Directly edit the `guides.yml` file in the GitHub web interface.

## Method 1: Edit Locally using VS Code
1. Open a (Windows) PowerShell Terminal
2. Navigate to the directory where you want to clone the repository
3. Clone the repository using the command:
    ```powershell
    git clone https://github.com/MDLutoronto/tutorials-search.git
    ```
4. Change directory to the cloned repository in the terminal:
    ```powershell
    cd tutorials-search
    ```
5. Switch to a new git branch for your edits (optional but strongly recommended):
    ```powershell
    git checkout -b update-tutorials # You can change 'update-tutorials' to a more descriptive branch name
    ```

6. Open the repository in VS Code using the command:
    ```powershell
    code .
    ```

7. A VS Code window will open. In the Explorer pane, navigate to `_data/guides.yml` and open it.
8. Edit the `guides.yml` file to add or modify tutorial records.
9. Save the changes and make a commit in the terminal:
    ```powershell
    git add _data/guides.yml
    git commit -m "Updated tutorial records"  # Add a meaningful commit message within the quotes
    git push origin main
    ```
10. Your changes will be pushed to the GitHub repository. You should see an alert in the repository to create a Pull Request.
11. Create a Pull Request for your changes. There will be some automated checks that run. Once they pass, you can click on the `Squash and merge` button to merge your changes into the main branch.
12. Your changes will be live on the tutorials-search site shortly after the merge.

## Method 2: Edit Directly in GitHub Web Interface
1. Navigate to the [tutorials-search repository](https://github.com/MDLutoronto/tutorials-search) in a web browser.
2. Create a new branch for your edits (optional but strongly recommended):
   1. Click on the X Branch button next to the `main` branch icon.
    <img src="{{ '/assets/images/tutorial-search-edit/branches_list.png' | relative_url }}" 
        alt="Branches list button on GitHub"
        style="width:300px; display:block; margin:auto;">
   2. You will see 'New branch' green button on the right side. Enter a name for your new branch (e.g. `update-tutorials`), and select `main` in the _Source_ option.
   3. You should see the branch under the `Your branches` section. Click on it to switch to the new branch.
    <img src="{{ '/assets/images/tutorial-search-edit/switch_to_new_branch_gh.png' | relative_url }}" 
          alt="Switch to new branch on GitHub"
          style="width:600px; display:block; margin:auto;">
   4. You should see `update-tutorials` next to the branch icon now.
    <img src="{{ '/assets/images/tutorial-search-edit/new_branch_after_switch.png' | relative_url }}" 
            alt="After switching to new branch"
            style="width:300px; display:block; margin:auto;">
3. Navigate to the `_data` folder and click on the `guides.yml` file. Click on the pencil icon at the top right corner of the file view to edit the file.
   <img src="{{ '/assets/images/tutorial-search-edit/edit_this_file.png' | relative_url }}" 
        alt="Location of guides.yml file"
        style="width:800px; display:block; margin:auto;">
4. You will be lead to an online editor. Make your changes to the `guides.yml` file. Click on the `Commit changes` button at the top right corner when you are done.
5. A pop-up will appear.
   1. Enter a meaningful commit message and description for your changes at the `Commit message` column. 
   2. You can leave the `Extended description` column empty. Ensure that the option `Commit directly to the <your-branch-name> branch.` is selected. Click on the `Commit changes` button to save your changes to the branch.
   <img src="{{ '/assets/images/tutorial-search-edit/commit-changes-pop-up.png' | relative_url }}" 
        alt="Commit changes popup"
        style="width:300px; display:block; margin:auto;">
6. Your changes will be saved to the new branch. Click on the `tutorials-search` box to go back to the repository main page in the current branch.
    <img src="{{ '/assets/images/tutorial-search-edit/after-commit.png' | relative_url }}" 
        alt="After commit changes and back to repo main page"
        style="width:400px; display:block; margin:auto;">
7. You should see an alert to create a Pull Request for your changes. Click on the `Compare & pull request` button.
   <img src="{{ '/assets/images/tutorial-search-edit/after-commit-alert.png' | relative_url }}" 
        alt="Create Pull Request alert"
        style="width:400px; display:block; margin:auto;">
8. You will be lead to the Pull Request creation page. Scroll down and click the `Create pull request` button.
    <img src="{{ '/assets/images/tutorial-search-edit/create-pull-request.png' | relative_url }}" 
          alt="Create Pull Request page"
          style="width:600px; display:block; margin:auto;">
9.  You will be brought to a new page. There will be some automated checks that run. Once they pass, you can click on the `Squash and merge` button to merge your changes into the main branch.
    <img src="{{ '/assets/images/tutorial-search-edit/squash-and-merge.png' | relative_url }}" 
          alt="Squash and Merge button"
          style="width:400px; display:block; margin:auto;">
10. Your changes will be live on the tutorials-search site shortly after the merge.