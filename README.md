# Removing a commit on git...

This repo is intended to serve as an exemplar - I'm trying to keep the second commit in the repo, but remove the third entirely.


The commits are, from oldest to newest:

1. Initial commit (empty)
1. Permanent commit
1. Commit that was added, then removed from `master`, and `master` was force-pushed (thereby making it an orphan)

## Commands to create this situation

```
git init
git commit --allow-empty -m "Initial commit (empty)"
# Add your file
git add .
git commit -m "Permanent commit"
# Add another file
git commit -m "to be orphaned"
git push
git reset --hard HEAD~1
git push --force
```
