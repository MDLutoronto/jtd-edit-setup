---
title: Setup for Editing Just-the-Docs Sites
layout: page
nav_order: 1
description: The setup guide for editing Just-the-Docs sites for MDLutoronto
created_date: 2025-12-09
permalink: setup
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---


This tutorial will guide you through the setup on your local machine for editing just the docs sites for our MDLutoronto project.

# Prerequisite

## Accounts

1. GitHub account and to be added to the learning object repository under [MDLutoronto](https://github.com/MDLutoronto) GitHub Organization
    1. Managing GitHub Repo access for students
        
        TBD: link to the guide for MDL staff to add students to the GitHub repo

## Software

1. [Ruby](https://rubyinstaller.org/downloads/) (install the latest x64 version, e.g. [Ruby+Devkit 3.4.6-1 (x64)](https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-3.4.6-1/rubyinstaller-devkit-3.4.6-1-x64.exe)) 
2. [Git](https://git-scm.com/downloads) (install the Windows version)
3. [VS Code](https://code.visualstudio.com/)
    1. Recommended VS Code extensions to install: 
        1. [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens): for visually using git within VS Code
        2. [Path Autocomplete](https://marketplace.visualstudio.com/items?itemName=ionutvmi.path-autocomplete): for auto-completing file paths when editing markdown files
        3. [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): for spell checking when editing markdown files


# Configuration

## Installing software
A recommended order of installation would be:
1. VS Code
2. Git
3. Ruby


### Vs code
For VS Code, you can just keep the default installation options.

Once installed, you may install the recommended extensions listed above via the Extensions view in VS Code (Ctrl+Shift+X), by searching for the extension name and clicking on the Install button.

Or you may install them by visiting the extension links above and clicking on the `Install` button there. The button will redirect you to VS Code and prompt you to install the extension.

### Git
For Git, during the installation, make sure to select the following options when prompted:

1. <img src="{{ '/assets/images/git-install/vscode-default-editor.png' | relative_url }}" 
        alt="Choose VS Code as default editor for Git"
        style="width:500px; display:block; margin:auto;">

    When prompted to select the default editor used by Git, select **Use Visual Studio Code as Git's default editor**
2. <img src="{{ '/assets/images/git-install/git-credential-manager.png' | relative_url }}" 
        alt="Choose Git Credential Manager"
        style="width:500px; display:block; margin:auto;">
    
    Make sure the **Git Credential Manager** option is selected to enable Git credential manager for managing GitHub credentials


## Connect to GitHub using Git credential manager

{: .important }
> You would first need to install Git on your Windows environment

1. Open a (Windows) PowerShell Terminal
    <a href="{{ '/assets/images/01_powershell.gif' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/01_powershell.gif' | relative_url }}" 
        alt="Open PowerShell"
        style="width:600px; display:block; margin:auto;">
    </a>

2. Type the following command to make the Git credential manager to manage your GitHub credentials

    ```powershell
    git config --global credential.helper manage
    ```

3. Type the following command to login to your GitHub account

    ```powershell
    git credential-manager github login
    ```
    <img src="{{ '/assets/images/git-gh-login.png' | relative_url }}" 
        alt="Git credential manager GitHub login"
        style="width:300px; display:block; margin:auto;">

    A window (outside the terminal) will pop up and prompt you to login to your GitHub account. Click on the `Sign in with your browser` button. After logging in, you may close the web browser window and return to the PowerShell terminal.

4. Run the following command to verify your GitHub authentication

    ```powershell
    git credential-manager github list
    ```

## Setting up git user.name and user.email

{: .important }
> Note that the [user.name](http://user.name) and [user.email](http://user.email) input will be visible publicly. If you have any concerns, consider using the [email relay address for commit provided by GitHub](https://github.com/settings/emails). 
> 
> You can retrieve that email address the under Settings > Emails, after turning on the `Keep my email addresses private` option
>
> <a href="{{ '/assets/images/gh_private_email.png' | relative_url }}" target="_blank">
>    <img src="{{ '/assets/images/gh_private_email.png' | relative_url }}" 
>        alt="GitHub CLI Authentication"
>        style="width:1000px; display:block; margin:auto;">
>    </a>


1. Input the following to set your git user name and email. The email should be the same as the one on your GitHub account (or the  email relay address provided by GitHub)

    ```powershell
    git config --global user.name "Your Name"
    git config --global user.email "Your Email"
    ```

2. Check your settings with the following command. Look at the [`user.email`](http://user.email) and `user.name` rows. It should show the values you have set above.
    
    ```powershell
    git config --list
    ```

# Working with an existing guide

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

2. Type the command below to clone a GitHub repository; replace the git_link with the intended GitHub repository link

    ```powershell
    gh repo clone $git_link
    ```

    For example, if you want to clone the sandbox repository above (with the .git link https://github.com/MDLutoronto/just-the-docs-sandbox-students.git), you will input
    ```powershell 
    gh repo clone https://github.com/MDLutoronto/just-the-docs-sandbox-students.git
    ```

    {: .highlight-title }
    > Tip
    >
    > After copying something, you can right-click on the terminal to paste it.

    <a href="{{ '/assets/images/03_gh-clone.gif' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/03_gh-clone.gif' | relative_url }}" 
        alt="GitHub Repo Clone"
        style="width:600px; display:block; margin:auto;">
    </a>


## Enter the repository directory

1. Once you have cloned the repository, type `cd $directory_name` to *change the directory* (`cd`) of the terminal to the repository directory.
    
    The `directory_name` by default is the repository name. As for the example above, it is `just-the-docs-sandbox-students`

    {: .highlight-title }
    > Tip
    >
    > To utilize the auto-complete function (avoid typing the long string), type a few characters and press Tab to let the terminal finish it.

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