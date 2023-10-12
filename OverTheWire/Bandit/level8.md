# OverTheWire Bandit - Level 7 → Level 8

## Objective

Find the password for the next level, stored in the file `data.txt` next to the word "millionth".

## Write-Up

After SSH-ing into the current level using `ssh bandit7@bandit.labs.overthewire.org -p 2220` and the provided password, I navigate to the home directory where the `data.txt` file resides.

I use the `grep` command with the `-F` flag to search for the fixed string "millionth" within the file:

```bash
grep -F "millionth" data.txt
```

This quickly reveals the password for the next level: "TESKZC0XvTetK0S9xNwm25STk5iWrBvP".

## Concepts and Skills

- Text search with `grep`

## Useful Commands

### grep command

- `-F`: Search for a fixed string. Unlike the default behavior of `grep`, which uses regular expressions, this will look for exact matches of the string.

## Lessons Learned

- Using the `-F` flag with `grep` can make the search simpler and faster when you are looking for an exact string.

## Tags

- Text Search
- grep command
