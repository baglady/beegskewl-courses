![](https://raw.githubusercontent.com/baglady/beegskewl-courses/main/git/images/quick-reference.jpg)

## Common workflows and quick reference

**Standard feature branch workflow:**

```bash
# 1. Start fresh from main
git checkout main && git pull

# 2. Create your branch
git checkout -b my-feature

# 3. Work, commit often
git add <files>
git commit -m "describe what and why"

# 4. Push and open a PR
git push -u origin my-feature

# 5. After PR merged, clean up
git checkout main && git pull
git branch -d my-feature
git push origin --delete my-feature
```

**Keep a branch up to date mid-PR:**

```bash
git fetch origin
git rebase origin/main
git push --force-with-lease
```

**Quick reference:**

| Command | What it does | When |
|---|---|---|
| `git push` | Upload local commits to remote | After committing, before PR |
| `git push -u origin <branch>` | Push a new branch and track it | First push of a new branch |
| `git push --force-with-lease` | Force-push safely | After rebase on your own branch |
| `git pull` | Fetch + merge remote into local | Start of session, before push |
| `git pull --rebase` | Fetch + rebase local onto remote | Feature branches |
| `git fetch --prune` | Download refs, remove stale | After remote branches deleted |
| `git merge --abort` | Cancel a merge in progress | Conflicts too messy |
| `git rebase -i HEAD~N` | Squash/reword last N commits | Before opening a PR |
| `git revert <commit>` | Undo a commit (safe, public) | Rolling back a bad deploy |

**Golden rules:**
1. Pull before you push.
2. Never rebase shared branches.
3. Delete merged branches promptly.
4. Force-push only your own branches — never `main`.
5. Squash noisy commits before merge.
