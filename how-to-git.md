# How to do stuff in git

### Do not track changes to an existing file

[Source](https://www.karltarvas.com/2020/07/02/git-keep-file-but-ignore-changes.html), [this vs `gitignore`](https://stackoverflow.com/questions/26633782/what-is-the-difference-between-gitignore-and-git-update-index-assume-uncha), [docs](https://git-scm.com/docs/git-update-index)

```bash
# to do
git update-index --assume-unchanged local.env
# to undo
git update-index --no-assume-unchanged local.env
```

