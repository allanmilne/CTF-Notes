# OverTheWire Bandit - Level 8 → Level 9

## Objective

The password for the next level is stored in the file `data.txt` and is the only line of text that occurs only once.

## Write-Up

### Initial Exploration
After SSH-ing into the current level with `ssh bandit8@bandit.labs.overthewire.org -p 2220` and the password provided, I verify that `data.txt` is in the current directory by running `ls -la`.

### Strategy
Reading the `uniq` man page, I notice that `uniq` only identifies adjacent repeated lines. To make identical lines adjacent and removable by `uniq`, I need to `sort` the lines first.

### Solution
To find the unique line, I use `sort` to sort the lines of `data.txt` and pipe (`|`) that sorted output to `uniq -u`:

```bash
sort data.txt | uniq -u
```

This returns the password for the next level: "EN632PlfYiZbn3PhVK3XOGSlNInNE00t".

## Concepts and Skills
- Text filtering using `sort` and `uniq`
- Pipe (`|`) for chaining commands

## Useful Commands

### sort command
- Sort lines in a text file.

### uniq command
- `-u`: Output only unique lines that do not have duplicates in the sorted file.

### Piping and Redirection
- `|`: Used to pipe the output of one command as input to another command.

## Lessons Learned
- `uniq` only works with sorted input for identifying duplicate lines, making `sort` and `uniq` a powerful combination when looking for unique lines.

## Resources
An excellent article about piping and redirection is available [here](https://ryanstutorials.net/linuxtutorial/piping.php).

## Tags
- Text Filtering
- Piping
- sort and uniq commands
