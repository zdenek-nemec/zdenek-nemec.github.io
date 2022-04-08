# Git

Sources

* [Stack Overflow: Reset](https://stackoverflow.com/questions/1611215/remove-a-git-commit-which-has-not-been-pushed)

## Usage

### Reset

If you have not pushed your changes to remote:

```bash
git reset HEAD~1
```

Else if you have pushed your changes to remote:

```bash
git revert HEAD
```

## Troubleshooting

### Comment Character

In case Sublime Merge complains about comments starting with hash `#` character,
saying that empty messages are not allowed. It is because the hash is set as
default comment character. Solution is to change the comment character to
something else.

```bash
git config core.commentchar "^"
```
