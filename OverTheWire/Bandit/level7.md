# OverTheWire Bandit - Level 6 → Level 7

## Objective

Locate a file on the server that is:
- Owned by user bandit7
- Owned by group bandit6
- 33 bytes in size

## Write-Up

To find the file containing the password for the next level, I SSH into bandit6@bandit.labs.overthewire.org on port 2220. Upon landing in the home directory and checking its contents (`ls -la`), I find that it's empty. However, going up one level to `/home`, I find multiple directories.

Initially, I use the `find` command with multiple flags to filter by file size, user, and group. Despite finding some files, they all return "Permission denied" when attempting to `cat` them.

I then rerun the `find` command from the root directory `/`. The first attempt mixes the error messages "Permission denied" with the actual output, making it challenging to pinpoint the file I'm interested in. I then use redirection (`2>/dev/null`) to exclude those error messages, revealing just one file that meets the criteria: `/var/lib/dpkg/info/bandit7.password`.

To get the content of the file, I use a subshell command substitution with `cat`, revealing the password for the next level: 'z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S'

## Concepts and Skills

- File properties
- File permissions
- Command-line utilities (`find`, `cat`)
- Redirection and piping

## Useful

### find command

- Find by size: `find -type f -size 33c`
- Find by user: `find -user bandit7`
- Find by group: `find / -group bandit6`

### Count files in directory

- `ls -1U DIR_NAME | wc -l`: Count all files in a directory (unsorted for speed).

### Redirection and Piping

- `2>/dev/null`: Discard error messages.
- `2>&1`: Merge standard output and error.

## Commands

1. SSH into the level:
    ```bash
    ssh bandit6@bandit.labs.overthewire.org -p 2220
    ```
   Password: `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`

2. Check the current directory:
    ```bash
    ls -la
    ```

3. Navigate up a directory and check its content:
    ```bash
    cd ../; ls -laF
    ```

4. Run the find command from the root directory and exclude error messages:
    ```bash
    find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null
    ```

5. Use the find result with cat to reveal the password:
    ```bash
    cat $(find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null)
    ```

## References

- [How to Find Files in Linux Using the Command Line](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)
- [Count Files in a Directory](https://linuxize.com/post/count-files-in-directory-on-linux/)

## Lessons Learned

- Understand file permissions and how they may restrict the `find` command.
- Learn to use redirection to filter out "Permission denied" errors.

## Tags

- File Search
- Redirection
- find command
