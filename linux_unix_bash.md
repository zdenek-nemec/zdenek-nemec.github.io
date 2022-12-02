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

### Tar

| Synopsis                                | Example                               | Description                                                                      |
| --------------------------------------- | ------------------------------------- | -------------------------------------------------------------------------------- |
| `tar -cf ARCHIVE_FILE DATA_TO_ARCHIVE`  | `tar -cf archive.tar data_*`          | Create archive from files and directories                                        |
| `tar -zcf ARCHIVE_FILE DATA_TO_ARCHIVE` | `tar -zcf archive.tgz data_*`         | Create compressed archive, extensions `.tgz` and `.tar.gz` are viable            |
| `tar -xf ARCHIVE_FILE`                  | `tar -xf archive.tar`                 | Extract archive                                                                  |
| `tar -zxf ARCHIVE_FILE`                 | `tar -zxf archive.tgz`                | Extract compressed archive                                                       |
| `tar -tvf ARCHIVE_FILE`                 | `tar -tvf archive.tar`                | List the content of the archive, handles `.tar`, `.tgz` and `.tar.gz` extensions |

### Links

Symbolic link

```bash
# Synopsis
ln -s TARGET LINK_NAME

# Example
ln -s /dcs/data01/SOFTWARE/Python/Python3.7.8/bin/python3.7 python
```

### Switch

```bash
choice="A"
case $choice in
    A)
        echo "First case"
        ;;
    B)
        echo "Second case"
        ;;
    *)
        echo "Default"
        ;;
esac
```

### Dictionary

```bash
declare -A dictionary=(
    ["Hello"]="Ahoj"
    ["One"]="Jedna"
)

echo "Hello in Czech is" ${dictionary["Hello"]}
echo "One in Czech is" ${dictionary["One"]}
echo "Two in Czech is" ${dictionary["Two"]}

echo "Known Czech words (values) are:" ${dictionary[@]}
echo "Known English words (keys) are:" ${!dictionary[@]}

# Output:
# Hello in Czech is Ahoj
# One in Czech is Jedna
# Two in Czech is
# Known Czech words (values) are: Ahoj Jedna
# Known English words (keys) are: Hello One
```

### Xargs

Sources

* [Tecmint](https://www.tecmint.com/xargs-command-examples/)
* [LinuxHint](https://linuxhint.com/xargs_linux/)

Just print the content of current directory

```bash
ls -1 | xargs
```

Print the command before executing

```bash
ls -1 | xargs -t
```

Prompt (Y/N) before executing

```bash
ls -1 | xargs -p
```

Use specific delimiter

```bash
echo -n "123-456-789" | xargs -n 1 -d "-" echo
```

Argument

```bash
ls -1 | xargs -I {} echo prefix_{}_suffix
```
