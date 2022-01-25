# Bash

## Detach Process

Suspend the process, run it on the background and keep going even when the SSH session is closed.

```bash
<command>
Ctrl + Z
bg
disown -h %1
```

`%1` is ID of the process, if there are multiple processes, use the correct ID.
