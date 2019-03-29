## `merge conflict`

A `merge conflict` occurs when two or more people attempt to edit the same content (e.g. when two people changed the same lines in a file or if one  deleted a file while another was modifying it.) 

**This is why we usually work in isolated `branches`.**

To resolve a `merge conflict`, we need to identify the conflicted file using `git status`, and decide which changes to keep or whether to incorporate all the changes. Conflicted changes will be identified within the file with conflict markers `<<<<<<<<`, `=========`, `>>>>>>>>`. Once the conflicted file is fixed, add/commit/push.

## `pull`

`git pull` gets the latest changes from the origin and merges them. `git pull` runs `git fetch` with the given parameters and calls `git merge` to merge the retrieved branch heads into the current branch.

## `merge ` and `rebase`

In git, there are two main ways to integrate changes from one branch into another: the `merge` and the `rebase`.

`Merge` incorporates changes from two branches without changing either of the existing branches. It simply creates a new `merge commit`.

`Rebase` moves the entire feature branch to begin on the tip of the master branch, effectively incorporating all of the new commits in master. But, instead of using a merge commit, rebasing re-writes the project history by creating brand new commits for each commit in the original branch. See [Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

## `reset`

`reset`, `revert`, and `clean` are all ways to 'undo' a commit. See [Undoing Commits & Changes](https://www.atlassian.com/git/tutorials/undoing-changes)

`Reset` moves the branch that `HEAD` is pointing to and optionally updates the index and the working directory (Where `HEAD` is the last commit snapshot, next commit parent, index is the proposed next commit snapshot - where a file goes when `git add` is run, and working directory is the sandbox). This means if `HEAD` is set to the master branch (i.e. you’re currently on the master branch), running `git reset` 9e5e6a4 will start by making master point to 9e5e6a4. Essentially, it undoes the last `git commit`. We have three options: `soft`, `mixed`, and `hard`, representing different stages of `reset`:

1. `soft`: Move the branch `HEAD` points to 
2. `mixed`: Make the index look like `HEAD` 
3. `hard`: Make the working directory look like the index

See [Reset Demystified](https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified)

## `revert`

With `revert`, git will create a new commit with the inverse of the last commit. 

## `Clean`

Undoes changes to the working directory.
