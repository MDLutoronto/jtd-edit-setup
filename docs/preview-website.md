---
title: Preview the website
layout: page
nav_order: 4
description: Guide on previewing website locally
created_date: 2026-02-12
has_children: False
parent: Edit, Preview and Publish
permalink: /preview-website/
staff: 
   - name: Ken Lui
     link: https://library.utoronto.ca/staff/ken-lui
---

# Preview the website locally
Before you publish the changes to the live site, you can preview the website locally on your machine to review the changes you made.

Assuming you are in the VS code terminal and in the root directory of the cloned repository, you can run the following commands to start a local preview server.

1. Open the terminal in VS Code. You can select 'Terminal' > 'New Terminal' from the top navigation bar (you can also use the shortcut Ctrl+`).

    <a href="{{ '/assets/images/preview-site/open-terminal-in-vscode.png' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/preview-site/open-terminal-in-vscode.png' | relative_url }}" 
        alt="Annotated steps to open Terminal in VS Code"
        style="width:600px; display:block; margin:auto;">
    </a>

2. Run the following command to install the required dependencies and start the Jekyll server with live reload enabled:

    ```powershell
    bundle install && bundle exec jekyll serve --livereload
    ```

    <a href="{{ '/assets/images/preview-site/bundle-install-exec.png' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/preview-site/bundle-install-exec.png' | relative_url }}" 
        alt="Bundle Install and Jekyll Serve in PowerShell inside VS Code"
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

    <a href="{{ '/assets/images/preview-site/see-changes-in-web.png' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/preview-site/see-changes-in-web.png' | relative_url }}" 
        alt="A preview of the website in the web browser and the VS code editing window side by side"
        style="width:600px; display:block; margin:auto;">
    </a>



3. To stop the preview server, you can go back to the terminal (click on the terminal window in VS Code) and press Ctrl+C to stop the server. If you asked to 'Terminate batch job (Y/N)?', type 'Y' and press Enter (two times) to confirm stopping the server.

    <a href="{{ '/assets/images/preview-site/terminate.png' | relative_url }}" target="_blank">
    <img src="{{ '/assets/images/preview-site/terminate.png' | relative_url }}" 
        alt="Terminate Preview Server in PowerShell"
        style="width:600px; display:block; margin:auto;">
    </a>

## Next Steps
After previewing the website and ensuring the changes look good, you can follow the instructions in the [Publish the changes to GitHub]({{site.baseurl}}/publish-changes/) guide to publish the changes to GitHub and make the changes live on the website.