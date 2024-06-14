# git_hooks
Repository to store some git hooks.

## Hooks in this repo

* prepare_commit-msg:
  
  Automatically prepends commit message with the branch name (especially if branch is named after the Jira ticket id). Merge commit messages are not prepended.

## How this works?

1. Enable git templates:
    ```
    git config --global core.hooksPath '~/git_hooks'
    ```

    By default Git will look for your hooks in the `$GIT_DIR/hooks` directory. Set this to different path, e.g. `~/git-hooks/', and Git will try to find your hooks in that directory, e.g. `~/git-hooks/prepare-commit-msg` instead of in `$GIT_DIR/hooks/prepare-commit-msg`.

2. Write your hooks in `~/.git-hooks/`

3. Make sure the hook is executable.
    ```
    chmod a+x ~/git-hooks/prepare-commit-msg
    ```

Point 4 may not be needed anymore

4. Re-initialize git in each existing repo you'd like to use this in:
    ```
    git init
    ```

> NOTE: If you already have a hook defined in your local git repo, this will not overwrite it.
