# OverTheWire Bandit - Level 4

## Objective

The password for the next level is stored in a hidden file within the `inhere` directory.

## Concepts and Skills

- Working with Hidden Files
- File and Directory Operations in Linux

## Tools Used

- SSH client
- Linux terminal

## Pre-Requisites

- Completed Bandit Level 3
- SSH client installed
- Intermediate understanding of Linux terminal commands

## Code Snippets and Commands

1. SSH into the level with the password from the previous level:
    ```bash
    ssh bandit3@bandit.labs.overthewire.org -p 2220
    ```
   Use the password: `aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG`

2. Navigate to the `inhere` directory:
    ```bash
    cd inhere
    ```

3. List all files, including hidden ones:
    ```bash
    ls -la
    ```

4. Read the content of the hidden file `.hidden`:
    ```bash
    cat .hidden
    ```

## Solution Walkthrough

1. SSH into the level and navigate to the `inhere` directory, as instructed.

2. Using `ls -la` lists all files, including hidden ones. We see a file named `.hidden`.

3. Running `cat .hidden` reveals the password for the next level: `2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe`.

## Lessons Learned

- Understood the importance of the `-a` flag in `ls` for showing hidden files.

## Additional Resources

- N/A

## Tags

- Hidden Files
- File Operations
