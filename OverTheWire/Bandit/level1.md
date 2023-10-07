# OverTheWire Bandit - Level 1

## Objective

The password for the next level is stored in a file called `readme` located in the home directory. Use this password to log into `bandit1` using SSH.

## Concepts and Skills

- Basic Linux Commands
- File Operations

## Tools Used

- SSH client
- Linux terminal

## Pre-Requisites

- Completed Bandit Level 0
- SSH client installed
- Basic understanding of Linux terminal commands

## Code Snippets and Commands

1. List the files in the home directory:
    ```bash
    ls
    ```
2. Read the content of the `readme` file to get the password:
    ```bash
    cat readme
    ```

## Solution Walkthrough

1. After logging in as `bandit0`, the first step is to identify the files present in the home directory. The `ls` command accomplishes this, revealing a file named `readme`.

2. The next step is to read the content of the `readme` file using the `cat` command, which displays the password for the next level: "NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL".

## Lessons Learned

- How to list files using `ls`.
- How to read file content using `cat`.

## Additional Resources

- Linux Commands: [Linux Command Tutorial](https://linuxcommand.org/)

## Tags

- Linux Commands
- File Operations
