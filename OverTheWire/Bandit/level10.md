# OverTheWire Bandit - Level 10 → Level 11

## Objective

The password for the next level is stored in the file `data.txt`, which contains base64 encoded data.

## Write-Up

### Initial Exploration
After logging into the level with `ssh bandit10@bandit.labs.overthewire.org -p 2220` and the password 'G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s', I run `ls -la` to identify the `data.txt` file. Using `cat data.txt` reveals that the content appears to be base64 encoded.

### Strategy
Since the file contains base64 encoded data, the `base64` command can be used to decode it. The `-d` or `--decode` option allows us to decode data.

### Solution
Unfamiliar with the `base64` command, I read the manual page. Running `man base64` confirms that the `-d` flag is used for decoding.

I then execute:

```bash
base64 -d data.txt
```

This decodes the base64 content and outputs the string "The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM", revealing the password for the next level.

## Concepts and Commands Used

- `base64 -d`: Decodes base64 encoded data.

## Lessons Learned

- The `base64` command in Linux is a simple yet effective tool for encoding and decoding base64 data.

## Tags
- Base64 Encoding and Decoding
- `base64` command
