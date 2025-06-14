# How to do stuff in git

### Do not track changes to an existing file

[Source](https://www.karltarvas.com/2020/07/02/git-keep-file-but-ignore-changes.html), [this vs `gitignore`](https://stackoverflow.com/questions/26633782/what-is-the-difference-between-gitignore-and-git-update-index-assume-uncha), [docs](https://git-scm.com/docs/git-update-index)

```bash
# to do
git update-index --assume-unchanged local.env
# to undo
git update-index --no-assume-unchanged local.env
```
### Working on Git issues with a stale or fast-updating main

Situation (stale main):
- Create many issues
- Create merge requests and branches for all issues at the same time
- Fix issues one by one and merge them into the main

Problem:
Because all branches were created from an older version of the main, they need to be up-to-date with the main before fixing the issue.

Solution:
- Go to your feature branch: 
git checkout my-branch
- Fetch the latest changes:
git fetch origin
- Merge or rebase main into your branch:
 - option 1: merge with a commit
 git merge origin/main
 - option 2: rebase to keep the history clean
 git rebase origin/main
- Resolve conflicts if needed and push
git push origin my-branch

