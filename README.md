# Map and Data Library Just the Docs editing guide

This is the editing guide for the Just the Docs sites for the Map and Data Library. It contains the initial setup instructions and how to preview the site locally when editing.

See https://mdlutoronto.github.io/jtd-edit-setup/.

## Editing this guide

### To preview the website

1. Run bundle install  to install the necessary files to start the preview server

    ```powershell
    bundle install
    ```
2. Run the following command to start the Jekyll server with live reload enabled

    ```powershell
    bundle exec jekyll serve --livereload
    ```

    Once you see the following message in the terminal, you may access the preview pages in your preferred web browser via http://127.0.0.1:4000 (or whatever address the terminal shows after the Server address line)

    ```text
    ...
    You can add fiddle to your Gemfile or gemspec to silence this warning.
    LiveReload address: http://127.0.0.1:35729
        Server address: http://127.0.0.1:4000
    Server running... press ctrl-c to stop.
    ```