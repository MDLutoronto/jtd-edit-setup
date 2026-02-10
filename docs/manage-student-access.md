---
title: Manage Student Access to MDLutoronto GitHub Repository
layout: page
nav_order: 1
description: The setup guide for granting access for students to the MDLutoronto GitHub repository for editing the just-the-docs sites.
created_date: 2026-02-10
permalink: /manage-student-access/
parent: Setup for Editing Just-the-Docs Sites
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---

# Introduction
This tutorial will guide you how to add students to the MDLutoronto GitHub repository, which is necessary for them to edit the just-the-docs sites.

# Adding students to 'Students' team
1. <img src="{{ '/assets/images/manage-student-access/mdl-gh-mainpage-teams.png' | relative_url }}" 
        alt="MDLutoronto GitHub repository main page with Teams tab highlighted"
        style="width:800px; display:block; margin:auto;">

    Go to the MDLutoronto <a href="https://github.com/MDLutoronto" target="_blank">GitHub repository main page</a>. Click on the "Teams" tab to view the list of teams in the repository.

2. <img src="{{ '/assets/images/manage-student-access/student-teams.png' | relative_url }}" 
        alt="List of teams in the MDLutoronto GitHub repository with the 'Student' team highlighted"
        style="width:800px; display:block; margin:auto;">
    
    Scroll down and find the "Students" team. Click on the "Students" team.

3. <img src="{{ '/assets/images/manage-student-access/add-a-member.png' | relative_url }}" 
        alt="'Students' team page with 'Add a member' button highlighted"
        style="width:800px; display:block; margin:auto;">
    
    On the "Students" team page, click on the "Add a member" button.

4. <img src="{{ '/assets/images/manage-student-access/search-and-add.png' | relative_url }}" 
        alt="'Students' team page with search and add member section highlighted"
        style="width:400px; display:block; margin:auto;">
    
    Search for the student's GitHub username (handle). Once you find the correct username, click on it, and then click the "Add $username to Students" button to add the student to the team.

# Add 'Students' team to repository with write access

For new tutorials, you will need to add the 'Students' team to the repository with write access. This only needs to be done once for each repository.

1. <img src="{{ '/assets/images/manage-student-access/repo-settings.png' | relative_url }}" 
        alt="MDLutoronto GitHub repository main page with 'Settings' tab highlighted"
        style="width:800px; display:block; margin:auto;">

    First, go to the repository's main page. Click on the "Settings" tab.
2. <img src="{{ '/assets/images/manage-student-access/add-teams-to-repo.png' | relative_url }}" 
        alt="Repository settings page with 'Collaborators and teams' option highlighted with number 1 annotation in the left sidebar, and the 'Add teams' button highlighted in the main section with number 2 annotation, and the 'Students' team highlighted in the dropdown menu with number 3 annotation"
        style="width:800px; display:block; margin:auto;">
   
   Select the 'Collaborators and teams' option from the left sidebar. Click on the "Add teams" button, and select the "Students" team from the dropdown menu.
3. <img src="{{ '/assets/images/manage-student-access/invite-students-with-write.png' | relative_url }}" 
        alt="Invitation form with 'Write' option selected, and highlighted with number 1 annotation, and the 'Add selection' button highlighted with number 2 annotation"
        style="width:400px; display:block; margin:auto;">
    Select the 'Write' option, and click the 'Add selection' button to grant the 'Students' team write access to the repository.

<img src="{{ '/assets/images/manage-student-access/write-permission-confirmation.png' | relative_url }}" 
        alt="Confirmation message for granting write access to the 'Students' team, with 'Role: write' displayed next to the 'Students' team in the list of teams with access to the repository"
        style="width:800px; display:block; margin:auto;">
You should now see the confirmation message, and the 'Role: write' is displayed next to the 'Students' team in the list of teams with access to the repository.