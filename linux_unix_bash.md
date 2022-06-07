# Linux/Unix + Bash

## How To

### Detach Process

Suspend the process, run it on the background and keep going even when the SSH session is closed.

```bash
COMMAND
Ctrl + Z
bg
disown -h %1
```

`%1` is ID of the process, if there are multiple processes, use the correct ID.

### SSH Key

Generate SSH key pair.

```bash
ssh-keygen -b 2048 -t rsa
```
