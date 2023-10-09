# OverTheWire Bandit - Level 1 → Level 2

## Objective

The password for the next level is stored in a file called `-` located in the home directory.

## Concepts and Skills

- Advanced File Operations
- Special Characters in Filenames

## Tools Used

- SSH client
- Linux terminal

## Pre-Requisites

- Completed Bandit Level 1
- SSH client installed
- Basic to Intermediate understanding of Linux terminal commands

## Code Snippets and Commands

1. SSH into the level with the password from the previous level:
    ```bash
    ssh bandit1@bandit.labs.overthewire.org -p 2220
    ```
   Use the password: `NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL`

2. List files in the home directory:
    ```bash
    ls
    ```

3. Attempt to read the file named `-`:
    ```bash
    cat -
    ```
   This doesn't yield the desired result.

4. Read the content of the file using its relative path:
    ```bash
    cat ./-
    ```

## Solution Walkthrough

1. After SSHing into the level, listing the files reveals a file named `-`.

2. A naïve attempt to read this file using `cat -` doesn't work, as the dash character `-` is interpreted as a special character for standard input in UNIX systems.

3. Searching online for "read dashed filename" gives us insights into handling files with special characters. Using the relative path `./-` allows us to explicitly specify the file we want to read.

4. Running `cat ./-` reveals the password for the next level: 'rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi'.

## Lessons Learned

- Some characters have special meanings in the Linux terminal.
- Files with special characters can be accessed using their relative or absolute path.

## Additional Resources

- [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](https://www.tldp.org/LDP/abs/html/special-chars.html)

## Tags

- Special Characters
- Advanced File Operations
