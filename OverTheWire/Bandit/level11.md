# OverTheWire Bandit - Level 11 → Level 12

## Objective

The password for the next level is stored in the file `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

## Write-Up

### Initial Exploration
After SSHing into the level with `ssh bandit11@bandit.labs.overthewire.org -p 2220` and the password '6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM', I run `ls -la` and see the `data.txt` file. A quick `cat data.txt` reveals jumbled text: "Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi."

### Strategy
Since the text has been rotated 13 places according to ROT13, the task is to reverse this operation to get the original text. The `tr` command can perform such character-based translation, which makes it a perfect fit for this task.

### Solution
Upon reading the `man tr` and understanding its syntax, the strategy involves shifting each character 13 places back to its original position. The `tr` command syntax is as follows:

```bash
tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```

Here's the breakdown:

- `N-ZA-M` corresponds to shifting uppercase letters by 13 positions.
- `n-za-m` corresponds to shifting lowercase letters by 13 positions.

Combining this with the `cat` command to read `data.txt`, the entire command becomes:

```bash
cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```

Executing this command outputs "The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv," which is the password for the next level.

## Concepts and Commands Used

- `tr`: Translate characters.
- `cat`: Concatenate and display the content of files.
- `|`: Piping to send the output of one command as input to another.

## Lessons Learned

- `tr` is a useful command for text transformations, including cryptographic techniques like ROT13.

#### ROT13 Example with Explanation

ROT13 (Rotate by 13 places) is a simple substitution cipher that replaces a letter with the letter 13 places down the alphabet. The alphabet wraps circularly; 'z' is followed by 'a'.

**Example**:  
Syntax: `echo "hello" | tr 'a-zA-Z' 'n-za-mN-ZA-M'`  
Output: `uryyb`

In the syntax `tr 'a-zA-Z' 'n-za-mN-ZA-M'`:

- `a-zA-Z`: Specifies the range of characters to be translated. It includes all lowercase (`a-z`) and uppercase (`A-Z`) letters.

- `n-za-mN-ZA-M`: Specifies the range of characters to replace the originals with. Each letter will be replaced with the letter 13 positions down the alphabet, wrapping back to the start if needed.

The command `tr 'a-zA-Z' 'n-za-mN-ZA-M'` therefore translates each alphabetic character to its counterpart 13 places down the alphabet, effectively applying the ROT13 cipher to the input text.

## Resources
- [Tr Command in Linux with Examples](https://linuxize.com/post/linux-tr-command/)
- [Caesar Cipher Gist](https://gist.github.com/IQAndreas/030b8e91a8d9a407caa6)

## Tags
- ROT13
- Text Transformation
- Character translation

