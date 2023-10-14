### Linux `strings` Command Cheat Sheet

#### Basic Usage

- Extract printable strings from a file.
`strings file.bin`

- Extract strings from multiple files.
`strings file1.bin file2.bin`

#### Output Options

- Display offset of the string in the file.
`strings -o file.bin`

- Display file name for each string (useful with multiple files).
`strings -f file1.bin file2.bin`

#### Length and Format

- Show strings of at least N characters long.
`strings -n N file.bin`

- Use different character encoding.
`strings -e S file.bin`

#### Filtering

- Only display strings that match a pattern.
`strings file.bin | grep 'pattern'`

#### Reading from Standard Input

- Read data from standard input.
`cat file.bin | strings`

#### Combining with Other Commands

- Use with `grep` to filter output.
`strings file.bin | grep 'http'`

- Use with `wc` to count strings.
`strings file.bin | wc -l`
