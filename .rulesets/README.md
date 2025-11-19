# Add ruleset(s) using CLI

## Prerequisite
You need to have [GitHub CLI](https://cli.github.com/) installed and authenticated.


## Command to add ruleset
Replace the `$REPONAME` with your repository name, and the file name (`$FILENAME`) of the ruleset JSON file, then run the following command in your terminal:

```bash
gh api -X POST /repos/mdlutoronto/$REPONAME/rulesets --input .rulesets/$FILENAME.json
```

For example, to add the `ci` ruleset to the `jtd-theme` repository, you would run:

```bash
gh api -X POST /repos/mdlutoronto/jtd-theme/rulesets --input .rulesets/ci.json
```

## Bulk Add All Rulesets
To add all rulesets in the `.rulesets` directory, you can wildcard the file name like this:

```bash
gh api -X POST /repos/mdlutoronto/$REPONAME/rulesets --input .rulesets/*.json
```
This command will add all JSON files in the `.rulesets` directory as rulesets to the specified repository.