![](https://raw.githubusercontent.com/baglady/beegskewl-courses/main/git/images/merge.jpg)

## git merge — combining branches

`git merge` takes the commits from one branch and integrates them into another. Run it from the branch you want to receive the changes.

```bash
git checkout main
git merge my-feature   # brings my-feature's commits into main
```

**Two kinds of merge:**

**Fast-forward:** Your target branch has not moved since the feature branch split off. Git just moves the branch pointer forward — no merge commit, clean history.

```
main:    A---B
feature:       C---D
after:   A---B---C---D
```

**3-way merge:** Both branches have new commits since they diverged. Git creates a merge commit with two parents.

```
main:    A---B-------M
feature:       C---D/
```

**When to merge vs rebase:**

| Situation | Use |
|---|---|
| Bringing a finished feature into main | merge (preserves the feature as a unit) |
| Updating your feature branch with the latest main | rebase (keeps history linear) |
| Shared branch that others have checked out | merge (never rebase shared history) |

**Resolving conflicts:** Git marks them with `<<<<<<<`, `=======`, `>>>>>>>`. Edit the file to the correct result, then `git add <file>` and `git commit` (or `git merge --continue`).

**Aborting:** `git merge --abort` puts everything back to before the merge started.
