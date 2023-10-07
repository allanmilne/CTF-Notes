# OverTheWire Bandit - Level 5

## Objective

The password for the next level is stored in the only human-readable file within the `inhere` directory.

## Concepts and Skills

- File Types and Readability
- Bash Loops
- Basic Scripting

## Tools Used

- SSH client
- Linux terminal

## Pre-Requisites

- Completed Bandit Level 4
- SSH client installed
- Basic understanding of Bash scripting and Linux terminal commands

## Code Snippets and Commands

1. SSH into the level:
    ```bash
    ssh bandit4@bandit.labs.overthewire.org -p 2220
    ```
   Use the password: `2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe`

2. Navigate to the `inhere` directory and list all files:
    ```bash
    cd inhere
    ls -la
    ```

3. Loop through the files to identify the human-readable file:
    ```bash
    for i in {0..9}; do
      filename="-file0$i"
      echo "$filename"
      cat -- "$filename"
      echo  # This adds a blank line after the file content
    done
    ```

## Solution Walkthrough

1. SSH into the level and navigate to the `inhere` directory.

2. Use `ls -la` to see that there are 10 files with similar names: `-file00` to `-file09`.

3. Create a Bash loop to iterate through these files and use `cat` to output their contents. The loop is augmented with `echo` statements to identify which file contains the readable text.

4. The human-readable file turns out to be `-file07`. Running `cat ./-file07` reveals the password for the next level: `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`.

## Lessons Learned

- Learned how to automate file reading with Bash loops.
- Reinforced the importance of verifying file types and readability.

## Additional Resources

- N/A

## Tags

- File Types
- Bash Looping
