# git_hooks
Repository to store some git hooks.

## Hooks in this repo

* prepare_commit-msg:
  
  Automatically prepends commit message with the branch name (especially if branch is named after the Jira ticket id). Merge commit messages are not prepended.

## How this works?

1. Enable git templates globally:
    ```
    git config --global core.hooksPath '~/git_hooks'
    ```

    By default Git looks for your hooks in the `$GIT_DIR/hooks` directory. However, this global setting sets this to different path, e.g. `~/git-hooks/`, and Git will try to find your hooks in that directory, e.g. `~/git-hooks/prepare-commit-msg` instead of in `$GIT_DIR/hooks/prepare-commit-msg`.

2. Write your hooks in `~/.git-hooks/`

3. Make sure the hook is executable.
    ```
    chmod a+x ~/git-hooks/prepare-commit-msg
    ```
