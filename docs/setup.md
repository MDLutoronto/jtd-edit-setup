---
title: Setup for Editing Just-the-Docs Sites
layout: page
nav_order: 1
description: The setup guide for editing Just-the-Docs sites for MDLutoronto
created_date: 2025-12-09
permalink: setup
has_children: true
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---


This tutorial will guide you through the setup on your local machine for editing just the docs sites for our MDLutoronto project.

# Prerequisite

## Accounts

1. GitHub account and to be added to the learning object repository under [MDLutoronto](https://github.com/MDLutoronto) GitHub Organization
   1. See the <a href="{{ '/manage-student-access/' | relative_url }}">Manage Student Access to MDLutoronto GitHub Repository</a> guide for instructions on how to add students to the repository.
    

## Software

1. [Ruby](https://rubyinstaller.org/downloads/) (install the 3.4.6-1 (x64) version, i.e. [Ruby+Devkit 3.4.6-1 (x64)](https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-3.4.6-1/rubyinstaller-devkit-3.4.6-1-x64.exe)) 
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

Once you have installed Git, follow the steps below for configuring Git credential manager and setting up git `user.name` and `user.email`.

#### Connect to GitHub using Git credential manager

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
    It's normal no output will be shown in the terminal after running this command.

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
    You should see your GitHub username printed in the terminal output

#### Setting up git user.name and user.email

{: .important }
> Note that the `user.name` and `user.email` input will be visible publicly. If you have any concerns, consider using the [email relay address for commit provided by GitHub](https://github.com/settings/emails). 
> 
> You can retrieve that email address the under Settings > Emails, after turning on the `Keep my email addresses private` option
>
> <a href="{{ '/assets/images/gh_private_email.png' | relative_url }}" target="_blank">
>    <img src="{{ '/assets/images/gh_private_email.png' | relative_url }}" 
>        alt="GitHub CLI Authentication"
>        style="width:1000px; display:block; margin:auto;">
>    </a>


1. Input the following to set your git user name and email. The email should be the same as the one on your GitHub account (or the  email relay address provided by GitHub)

    User name can be any name you want to show up on your commits: 
    ```powershell
    git config --global user.name "Your Name"
    ```
    User email should be the email address associated with your GitHub account (or the email relay address provided by GitHub):
    ```powershell
    git config --global user.email "Your Email"
    ```

2. Check your settings with the following command:
    
    ```powershell
    git config --list
    ```

    Look at the `user.email` and `user.name` row, like the following:

    ```text
    ...
    user.name=Your Name
    user.email=Your Email
    ...
    ```

### Ruby
For Ruby, during the installation, default options should be fine. 

However, at the end of the installation, make sure to check uncheck the `Run 'ridk install' to set up MSYS2 and development toolchain` option before clicking on the Finish button.
<img src="{{ '/assets/images/uncheck-msys2.png' | relative_url }}" 
        alt="Uncheck Run ridk install"
        style="width:500px; display:block; margin:auto;">


# Next steps

## New guide
See the <a href="{{ '/create-new-guide/' | relative_url }}">Create a new guide</a> page for instructions on how to create a new Just-the-Docs guide.

## Existing guide
See the <a href="{{ '/edit-guide/' | relative_url }}">Edit a guide</a> page for instructions on how to work with an existing Just-the-Docs guide.