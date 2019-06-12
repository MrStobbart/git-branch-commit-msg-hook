# Git Commit Message Hook

## Installation

This script is a [git hook](https://githooks.com/) that adds the branch and feature id to the commit message. To use it in a git repository copy the `commit-msg` file into your `.git/hooks/` folder.

## Formating

When the branchname has the following format: `[type]/[id1]/[name]` The type and id will be prefixed for each commit. Each commit will then have the following format: `[type] #[id]: [commitMessage]`.

Example: (branch name)`feature/182/Implement-password-reset` -> (creates commit messages)`feature #182: [commitMessage]`

* `[type]`: Type of the branch, usually `feature`or `bugfix`
* `[id]`: Id of the related issue/ticket. Should the branch be responsible for multiple issues/tickets they should be separated by a 'minus' (`-`). The hook always uses the string after the first `/` as id(s).
* `[name]`: A descriptive name of the branch. This will not be added to the commit message

If no id is present (e.g. master or develop branch) the hook will only add the branch name in front of the commit.

## How to ignore Hook for one Commit

If the branch name should be ignored for a commit, start the commit message with **`no-hook`** or **`no`** **followed by a space**. Don't forget to then add the branch tag and issue id manually. (`no-hook [branchTag] #[branchId]: [commitMessage]`)

Merge commits are also ignored by this hook, when they start with `Merge ` (remember the space).

Example: (commit message)`no bugfix #192: Fixed logging` -> (creates commit message)`bugfix #192: Fixed logging`
