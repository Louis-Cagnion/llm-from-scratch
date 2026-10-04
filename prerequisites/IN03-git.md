# IN03. Git

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 2. Core mathematics and programming | IN01 | every module with code, and L00 (hooks) |

## Why this module

All the code of the project lives in a Git repository published on GitHub: every experiment, every kernel and every fix is a commit, and the history itself is part of the portfolio. Git also protects against mistakes: a bad change can always be inspected and undone.

## Objectives

After this module, you can version a project cleanly, explore and repair its history, work with branches and remotes, resolve conflicts, and keep large data out of the repository.

## Competences evaluated

1. Explain Git's model: working tree, staging area, commits as snapshots, the commit graph, branches and `HEAD` as pointers.
2. Create a repository, stage and commit changes selectively (including parts of files), and write good commit messages.
3. Inspect the history and changes (`log`, `diff`, `show`, `blame`) and find when a line or a bug was introduced (`bisect`).
4. Undo changes at every level: unstaged edits, staged changes, the last commit, an old commit (`restore`, `reset`, `revert`), and recover lost work with `reflog`.
5. Create, switch and delete branches; merge them and explain fast-forward versus merge commits.
6. Resolve merge conflicts by hand.
7. Rebase a branch, and explain when rewriting history is safe and when it is not.
8. Work with a remote: clone, fetch, pull, push, upstream branches, SSH authentication with GitHub.
9. Write a `.gitignore`, keep datasets and weights out of the repository, and remove a file committed by mistake from the index.
10. Write a Git hook (for example a pre-commit hook that runs the tests).
11. Use tags for versions.

## Notions, in learning order

1. **Why version control**: snapshots, history, collaboration.
2. **Git's data model**: blobs, trees, commits, hashes, references, the commit graph.
3. **Everyday workflow**: `init`, `status`, `add` (and `add -p`), `commit`, commit message conventions.
4. **History**: `log` and its formats, `diff` between any two states, `show`, `blame`, `bisect`.
5. **Undoing**: `restore`, `reset` (soft, mixed, hard), `revert`, `reflog`, the danger of hard resets.
6. **Branches**: creation, switching, merging, fast-forward, merge commits.
7. **Conflicts**: how they arise, markers, resolution, aborting a merge.
8. **Rebase**: what it does to commits, interactive rebase (on a local machine), the rule never to rewrite published history.
9. **Remotes**: clone, fetch, pull, push, tracking branches, SSH keys, GitHub.
10. **Hygiene**: `.gitignore`, what never to commit (data, weights, secrets), `git rm --cached`.
11. **Automation**: hooks, tags.

## Practice

- Versioning every program of the other modules from now on, with meaningful commits.
- A sandbox repository where conflicts, resets and lost commits are created on purpose and then repaired.
- A pre-commit hook that runs a test script and refuses the commit when it fails.

## Evaluation format

One practical session, about 1 hour 30: a prepared repository with tasks to perform (inspect history, undo specific changes, merge with conflicts, rebase, recover a lost commit, write a hook) and short explanation questions. Pass mark 100 %.

## References

- Scott Chacon and Ben Straub, *Pro Git* (free book), chapters 1 to 3 and 7.
- MIT, *The Missing Semester of Your CS Education*, lecture on version control (free).
- *Learn Git Branching* (free interactive tutorial).
