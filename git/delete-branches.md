![](https://raw.githubusercontent.com/baglady/beegskewl-courses/main/git/images/delete-branches.jpg)

## Deleting old branches and cleaning up

Delete a feature or fix branch as soon as it is merged. Stale branches confuse everyone.

**Delete a local branch:**

```bash
git branch -d my-feature       # safe: refuses if unmerged
git branch -D my-feature       # force-delete even if unmerged
```

**Delete a remote branch:**

```bash
git push origin --delete my-feature
```

**Clean up stale remote-tracking refs:**

```bash
git fetch --prune              # removes stale origin/... refs in one go
```

**Squash messy commits before merge:**

```bash
git rebase -i HEAD~5    # opens an editor to squash the last 5 commits
```

Change `pick` to `squash` (or `s`) on commits you want folded into the one above.

**Undo a commit safely on shared branches:**

```bash
git revert <commit>     # new commit that undoes it — history preserved
```

**Prune all merged local branches at once:**

```bash
git branch --merged main | grep -v '\* main' | xargs git branch -d
```

Review the list before running.
