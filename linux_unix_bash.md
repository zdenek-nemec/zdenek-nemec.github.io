# Linux/Unix + Bash

## Detach Process

Suspend the process, run it on the background and keep going even when the SSH session is closed.

```bash
COMMAND
Ctrl + Z
bg
disown -h %1
```

`%1` is ID of the process, if there are multiple processes, use the correct ID.

## SSH Key

Generate SSH key pair.

```bash
ssh-keygen -b 2048 -t rsa
```

## Tar

Extensions

* `.tar` - Archive
* `.tar.gz` and `.tgz` - Compressed archive

Create archive from files and directories

```bash
# Synopsis
tar -cf ARCHIVE_FILE DATA_TO_ARCHIVE

# Examples
tar -cf archive.tar data_*.txt
tar -cf archive.tar data_directory
```

Create compressed archive

```bash
# Synopsis
tar -zcf ARCHIVE_FILE DATA_TO_ARCHIVE

# Examples
tar -zcf archive.tar.gz data_*.txt
tar -zcf archive.tgz data_*.txt
tar -zcf archive.tgz data_directory
```

Extract archive

```bash
# Synopsis
tar -xf ARCHIVE_FILE

# Example
tar -xf archive.tar
```

Extract compressed archive

```bash
# Synopsis
tar -zxf ARCHIVE_FILE

# Examples
tar -zxf archive.tar.gz
tar -zxf archive.tgz
```

List the content of the archive. Handles all extensions `.tar`, `tar.gz` and `.tgz`.

```bash
# Synopsis
tar -tvf ARCHIVE_FILE

# Examples
tar -tvf archive.tar
tar -tvf archive.tar.gz
tar -tvf archive.tgz
```

## Links

Symbolic link

```bash
# Synopsis
ln -s TARGET LINK_NAME

# Example
ln -s /dcs/data01/SOFTWARE/Python/Python3.7.8/bin/python3.7 python
```

## Switch

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

## Dictionary

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

## Xargs

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

## Generate File with Random Data

Sources

* [StackExchange](https://unix.stackexchange.com/questions/33629/how-can-i-populate-a-file-with-random-data)

```bash
head -c 10M </dev/urandom >random_data.dat

# If the head doesn't understand the M suffix, specify the size in bytes
head -c 10485760 </dev/urandom >random_data.dat

# If the head doesn't understand the -c option, use dd
dd if=/dev/urandom of=random_data.dat bs=1024 count=10240
```

## Rsync

Files

```bash
# Synopsis
rsync SOURCE_PATH DESTINATION_PATH

# Example
rsync ~/*.txt zdenek@ubuntu:/home
```

Directories - Will create the synchronized directory on the destination path

```bash
# Synopsis
rsync -r SOURCE_PATH DESTINATION_PATH

# Example
rsync -r ~/test_directory zdenek@ubuntu:/home
```
