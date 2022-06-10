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

```bash
# Synopsis
tar -zcf ARCHIVE_FILE TARGET

# Example
tar -zcf archive.tgz data
```

### Links

Symbolic link

```bash
# Synopsis
ln -s TARGET LINK_NAME

# Example
ln -s python3.7 python
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

# Output
# Hello in Czech is Ahoj
# One in Czech is Jedna
# Two in Czech is
# Known Czech words (values) are Ahoj Jedna
# Known English words (keys) are Hello One
```
