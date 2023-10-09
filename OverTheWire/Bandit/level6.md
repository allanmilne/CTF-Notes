# OverTheWire Bandit - Level 5 → Level 6

## Objective

Locate a file under the `inhere` directory that is:
- Human-readable
- 1033 bytes in size
- Not executable

## Write-Up

After successfully SSHing into the level, I navigated to the `inhere` directory. This directory contains several subdirectories named from `maybehere00` to `maybehere19`. The task is to find a human-readable file of a specific size (1033 bytes) that is not executable.

I chose to use the `find` command to search recursively for files that match the given criteria. The `find` command is versatile and offers several options to filter by file type and size. I used the `-type f` flag to specify that I was looking for regular files and `-size 1033c` to specify the file size in bytes.

Running this command, I located the file `./maybehere07/.file2` that met all the conditions. A quick `cat` of the file revealed the password for the next level.

## Concepts and Skills

- File properties
- Recursive search
- Bash commands (`find`, `cat`)

## Useful

### `find` command flags

**Find Files by Type**
- `f`: a regular file
- `d`: directory
- `l`: symbolic link
- `c`: character devices
- `b`: block devices
- `p`: named pipe (FIFO)
- `s`: socket

**Find Files by Size**
- `b`: 512-byte blocks (default)
- `c`: bytes
- `w`: two-byte words
- `k`: Kilobytes
- `M`: Megabytes
- `G`: Gigabytes

## Commands

1. SSH into the level:
    ```bash
    ssh bandit6@bandit.labs.overthewire.org -p 2220
    ```
   Password: `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`

2. Navigate to the `inhere` directory:
    ```bash
    cd inhere; ls -la
    ```

3. Use the `find` command to locate the file:
    ```bash
    find -type f -size 1033c
    ```

4. Reveal the password:
    ```bash
    cat ./maybehere07/.file2
    ```

## References

- [How to Find Files in Linux Using the Command Line](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)

## Lessons Learned

- The `find` command is a powerful tool for searching files based on multiple attributes.
- Using the `man` command to read the manual can be very helpful for understanding complex commands and their flags.

## Tags

- File Search
- Recursive Search
- find command
