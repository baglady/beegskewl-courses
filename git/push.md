## git push — sending your work to a remote

`git push` uploads commits from your local branch to a remote (GitHub, GitLab, etc.). The remote is usually named `origin`.

**Common forms:**

```bash
git push                      # push current branch to its tracked remote
git push origin main          # push local main to remote main
git push -u origin my-branch  # push a new branch and set it as the tracked remote
```

**When to push:**
- After committing locally and you want a backup or to share with others
- Before opening a pull request
- At the end of a work session on a shared branch

**When NOT to push yet:**
- You haven't tested it
- Your commits are messy and you plan to squash them first
- You are mid-rebase or mid-merge

**Force push (`git push --force` or `git push -f`):** Rewrites the remote branch to match yours, discarding any commits on the remote that yours doesn't have. This destroys other people's work if they have the same branch. Only use it on your own private feature branch, never on `main` or `develop`. `--force-with-lease` is safer — it refuses if someone else pushed since you last pulled.
