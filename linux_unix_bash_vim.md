# Vim

Sources

* [Vim help files](https://vimhelp.org/)

## How To

```bash
# Open two files with screen splitted horizontaly
vim -o a.txt b.txt

# Open two files with screen splitted vertically
vim -O a.txt b.txt
```

## Commands

| Command        | Description                          |
| -------------- | ------------------------------------ |
| `:e FILENAME`  | Open file for editing                |
| `:r FILENAME`  | Insert the content of file           |
| `:set nu`      | Enable row numbers                   |
| `:set nonu`    | Disable row numbers                  |
| `:set paste`   | Enable paste mod (do not autoindent) |
| `:set nopaste` | Disable paste mod                    |
| `:split`       | Split screen                         |

## Keyboard Shortcuts

| Shortcut                       | Description                      |
| ------------------------------ | -------------------------------- |
| `Ctrl + W`, `Shift + H`        | Split screen horizontaly         |
| `Ctrl + W`, `Shift + K`        | Split screen vertically          |
| `Ctrl + W`, `Left/Right Arrow` | Move cursor to left/right window |
| `Ctrl + W`, `Up/Down Arrow`    | Move cursor to up/down window    |
| `Ctrl + W`, `R`                | Rotate files in split-screen     |
