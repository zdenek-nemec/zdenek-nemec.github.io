# Git

Sources

* ...

## Troubleshooting

### Comment Character

In case Sublime Merge complains about comments starting with hash `#` character,
saying that empty messages are not allowed. It is because the hash is set as
default comment character. Solution is to change the comment character to
something else.

```bash
git config core.commentchar "^"
```
