# Git

Sources

* Download from [Git-SCM](https://git-scm.com/)
* [Stack Overflow: Reset](https://stackoverflow.com/questions/1611215/remove-a-git-commit-which-has-not-been-pushed)

---

## How To

### Merge and Squash

```bash
git merge --squash BRANCH
```

### Reset

If you have not pushed your changes to remote:

```bash
git reset HEAD~1
```

Else if you have pushed your changes to remote:

```bash
git revert HEAD
```

---

## Troubleshooting

### Home

Environment variable `HOME` must be set in Windows, otherwise the `.ssh`
directory will be in the default Windows home directory.

### Comment Character

In case Sublime Merge complains about comments starting with hash `#` character,
saying that empty messages are not allowed. It is because the hash is set as
default comment character. Solution is to change the comment character to
something else.

```bash
git config core.commentchar "^"
```
