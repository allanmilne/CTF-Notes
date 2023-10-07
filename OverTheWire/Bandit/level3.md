# OverTheWire Bandit - Level 3

## Objective

The password for the next level is stored in a file called `spaces in this filename` located in the home directory.

## Concepts and Skills

- Dealing with Special Filenames
- File Operations in Linux

## Tools Used

- SSH client
- Linux terminal

## Pre-Requisites

- Completed Bandit Level 2
- SSH client installed
- Intermediate understanding of Linux terminal commands

## Code Snippets and Commands

1. SSH into the level with the password from the previous level:
    ```bash
    ssh bandit2@bandit.labs.overthewire.org -p 2220
    ```
   Use the password: `rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`

2. List files in the home directory:
    ```bash
    ls
    ```

3. Read the content of the file named `spaces in this filename` using quotes:
    ```bash
    cat "spaces in this filename"
    ```

## Solution Walkthrough

1. After SSHing into the level, we discover a file with a tricky name containing spaces: `spaces in this filename`.

2. A quick Google search shows two approaches for dealing with filenames with spaces:
    - Wrap the filename in quotes.
    - Use a backslash (`\`) to escape each space.

3. We use the first approach, wrapping the filename in quotes: `cat "spaces in this filename"`. This correctly displays the password for the next level: `aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG`.

## Lessons Learned

- Learned how to handle filenames with spaces in the Linux terminal.

## Additional Resources

- [Linux Handbook - Dealing with Filenames with Spaces](https://linuxhandbook.com/filename-spaces-linux/)

## Tags

- Special Filenames
- Linux Terminal Skills
