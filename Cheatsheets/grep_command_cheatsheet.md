### Linux `grep` Command Cheat Sheet

#### Basic Usage

- Search for a pattern in a file.
`grep 'pattern' file.txt`

- Search recursively in directories.
`grep -r 'pattern' /path/to/dir`

#### Case Sensitivity

- Case-insensitive search.
`grep -i 'pattern' file.txt`

#### Line Numbers and File Names

- Show line numbers.
`grep -n 'pattern' file.txt`

- Show file name with the matched line.
`grep -H 'pattern' file.txt`

#### Context Lines

- Show N lines before the match.
`grep -B N 'pattern' file.txt`

- Show N lines after the match.
`grep -A N 'pattern' file.txt`

- Show N lines around the match.
`grep -C N 'pattern' file.txt`

#### Matching Variations

- Match whole words only.
`grep -w 'pattern' file.txt`

- Match beginning of lines.
`grep '^pattern' file.txt`

- Match end of lines.
`grep 'pattern$' file.txt`

#### Inverting Matches

- Show lines that do not match the pattern.
`grep -v 'pattern' file.txt`

#### Counting Matches

- Count matching lines.
`grep -c 'pattern' file.txt`

#### Using Regular Expressions

- Use extended regular expressions.
`grep -E 'pattern1|pattern2' file.txt`

#### Combining Options

- Combine multiple options.
`grep -i -n 'pattern' file.txt`
