# better-logseq-git-sync

Logseq points to https://github.com/CharlesChiuGit/Logseq-Git-Sync-101 as the default implementation
for git-based syncing, but their approach relies primarily on these two extremely primitive [pre- and post-commit hooks](https://github.com/CharlesChiuGit/Logseq-Git-Sync-101/tree/main/git-hooks),
which leave a lot to be desired from an error-handling and git history approach.

## Issues solved with this repo
* Clean linear history based on rebasing local changes against the canonical history in github/other git host
* Better error handling when merge conflicts do occur

