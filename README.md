# git_hooks
Repository to store some git hooks.

* prepare_commit-msg:
  
  Automatically prepends commit message with the branch name (especially if branch is named after the Jira ticket id). Merge commit messages are not prepended.

## How this works?

1. Enable git templates:
    ```
    git config --global init.templatedir '~/git_hooks'
    ```

    This tells git to copy everything in `~/git-hooks` to your per-project `.git/` directory when you run `git init`

2. Write your hooks in `~/.git-hooks/`

3. Make sure the hook is executable.
    ```
    chmod a+x ~/.git-templates/hooks/prepare-commit-msg
    ```

4. Re-initialize git in each existing repo you'd like to use this in:
    ```
    git init
    ```

> NOTE: If you already have a hook defined in your local git repo, this will not overwrite it.
