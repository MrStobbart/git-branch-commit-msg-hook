# git-branch-commit-msg-hook


This script is a [git hook](https://githooks.com/) for commit messages.

When the branchname has the correct format: `[type]/[id1]-[id2]/[name]` The type and id will be prefixed for each commit. Each commit will then have the following format: `[type] #[id] #[id]: [commitMessage]`.

* `[type]`: Type of the branch, usually `feature`or `bugfix`
* `[id]`: Id of the related issue/ticket. Should the branch be responsible for multiple issues/tickets they should be separated by a 'minus' (`-`). Each branch must have a id!
* `[name]`: A descriptive name of the branch. This will not be added to the commit message

If no id is present (e.g. master or develop branch) the hook will only add the branch name in front of the commit.

If the branch name should be ignored for a commit, start the commit message with **space separated** **`no-hook`** or **`no`**.

