![](https://raw.githubusercontent.com/baglady/beegskewl-courses/main/git/images/pull.jpg)

## git pull — getting changes from a remote

`git pull` is a shortcut for two commands run back to back:

1. `git fetch` — downloads remote commits without touching your files
2. `git merge` — merges those remote commits into your current branch

**Common forms:**

```bash
git pull                   # pull the tracked remote branch into current branch
git pull origin main       # pull remote main into your current branch
git pull --rebase          # replay your local commits on top instead of merging
```

**When to pull:**
- At the start of every work session, before you begin
- Before pushing, to pick up any changes others pushed while you were working
- Before merging a feature branch, to make sure main is up to date

**`git pull --rebase` vs plain pull:**

| | Plain pull | Pull --rebase |
|---|---|---|
| Result | Creates a merge commit | Replays your commits on top of remote |
| History | Branchy, shows the merge point | Linear, cleaner |
| Conflicts | Resolved once in the merge | Resolved per replayed commit |
| Best for | Shared long-lived branches | Personal feature branches |

`--rebase` is generally preferred on feature branches. Some teams enforce it as the default:
`git config pull.rebase true`

**`git fetch` alone:** Downloads remote changes without touching your branch. Safe to run any time.
