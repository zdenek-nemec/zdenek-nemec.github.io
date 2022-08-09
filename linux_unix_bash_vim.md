# Vim

Sources

* [Vim cheat sheet](https://vim.rtorr.com/)
* [Vim help files](https://vimhelp.org/)

## How To

```bash
# Open two files with screen splitted horizontaly (top and bottow)
vim -o a.txt b.txt

# Open two files with screen splitted vertically (left and right)
vim -O a.txt b.txt
```

## Commands

| Command        | Description                          |
| -------------- | ------------------------------------ |
| `:e FILENAME`  | Open the file for editing            |
| `:r FILENAME`  | Insert the content of the file       |
| `:set nu`      | Show row numbers                     |
| `:set nonu`    | Hide row numbers                     |
| `:set paste`   | Enable paste mod (do not autoindent) |
| `:set nopaste` | Disable paste mod                    |
| `:split`       | Split the screen                     |
| `:3`           | Go to 3rd line                       |

## Navigation

| Keyboard Shortcut | Description                     |
| ----------------- | ------------------------------- |
| `gg`              | Go to first line                |
| `G`               | Go to last line                 |
| `3gg`             | Go to 3rd line                  |
| `Ctrl` + `f`      | Forward one page                |
| `Ctrl` + `b`      | Backward one page               |
| `i`               | Insert before the cursor        |
| `a`               | Insert after the cursor         |
| `I`               | Insert at the start of the line |
| `A`               | Insert at the end of the line   |

## Managing Windows

| Keyboard Shortcut                | Description                      |
| -------------------------------- | -------------------------------- |
| `Ctrl` + `w`, `Shift` + `h`      | Split screen horizontaly         |
| `Ctrl` + `w`, `Shift` + `k`      | Split screen vertically          |
| `Ctrl` + `w`, `Left/Right Arrow` | Move cursor to left/right window |
| `Ctrl` + `w`, `Up/Down Arrow`    | Move cursor to up/down window    |
| `Ctrl` + `w`, `r`                | Rotate files in split-screen     |
