# better-logseq-git-sync

Logseq points to [CharlesChiuGit/Logseq-Git-Sync-101](https://github.com/CharlesChiuGit/Logseq-Git-Sync-101) as the default implementation
for git-based syncing, but their approach relies primarily on these [two extremely primitive pre- and post-commit hooks](https://github.com/CharlesChiuGit/Logseq-Git-Sync-101/tree/main/git-hooks),
which leave a lot to be desired from an error-handling and git history approach.

## Issues solved with this repo
* Clean linear history based on rebasing local changes against the canonical history in github/any other git host
* Better error handling when merge conflicts do occur
* Easy one-line installation of hooks, no need to manually run `chmod +x` for each of the hooks

## Installation
* Inside of your logseq directory, simply run:

```sh
# Run from the root of your logseq git repo
curl -L --remote-name-all --output-dir .git/hooks https://raw.githubusercontent.com/JasonYao/better-logseq-git-sync/main/git-hooks/{post,pre}-commit && chmod +x .git/hooks/post-commit .git/hooks/pre-commit
```

If you're interested, the curl flags used here mean:
* `-L`: Follow all redirects
* `--remote-name-all`: Enables us to fetch multiple files and use the {fileName1,fileName2} syntax in the url passed into curl
* `--output-dir .git/hooks`: Sets the files fetched to be piped into the `.git/hooks` directory

