# OverTheWire Bandit - Level 6

## Objective

The password for the next level is stored somewhere under the `inhere` directory and has all of the following properties:
- Human-readable
- 1033 bytes in size
- Not executable

## Concepts and Skills

- File properties
- Recursive search
- Bash commands (`find`, `cat`)

## Tools Used

- SSH client
- Linux terminal

## Pre-Requisites

- Completed Bandit Level 5
- SSH client installed
- Basic understanding of Linux terminal commands

## Code Snippets and Commands

1. SSH into the level:
    ```bash
    ssh bandit5@bandit.labs.overthewire.org -p 2220
    ```
   Use the password: `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`

2. Navigate to the `inhere` directory and list all files:
    ```bash
    cd inhere
    ls -la
    ```

3. Use `find` command to search for the file based on the properties:
    ```bash
    find -type f -size 1033c
    ```

## Solution Walkthrough

1. SSH into the level and navigate to the `inhere` directory.

2. Use `ls -la` to see multiple directories named `maybehere00` through `maybehere19`.

3. The `find` command is employed to perform a recursive search for files with specific characteristics.

4. Running `find -type f -size 1033c` reveals the file `./maybehere07/.file2`.

5. `cat ./maybehere07/.file2` reveals the password for the next level: `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`.

## Lessons Learned

- Familiarized with the `find` command and its flags for searching based on file properties.
- Understood the importance of recursive search when dealing with nested directories.

## Additional Resources

- [Man page for find command](https://linux.die.net/man/1/find)

## Tags

- File Search
- Recursive Search
- find command
