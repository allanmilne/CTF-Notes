### Linux `tr` Command Cheat Sheet

#### TL;DR on `tr` Command

The `tr` (translate or delete characters) command is used for translating, deleting, or squeezing repeating characters from standard input and writing the result to standard output. It is commonly used for text manipulation tasks.

**Example**:  
Input: `echo 'apple' | tr 'a' 'A'`  
Output: `Apple`

**Common Uses**:
- Replacing or removing characters.
- Converting text to uppercase or lowercase.
- Removing duplicate/redundant characters.

#### Basic Usage

- Translate characters.  
  **Example**: `echo 'hello' | tr 'a-z' 'A-Z'`  
  **Output**: `HELLO`

- Delete characters.  
  **Example**: `echo 'hello world' | tr -d ' '`  
  **Output**: `helloworld`

#### Case Conversion

- Convert to uppercase.  
  **Example**: `echo 'hello' | tr '[:lower:]' '[:upper:]'`  
  **Output**: `HELLO`

- Convert to lowercase.  
  **Example**: `echo 'HELLO' | tr '[:upper:]' '[:lower:]'`  
  **Output**: `hello`

#### Removing Repeating Characters

- Squeeze repeating characters.  
  **Example**: `echo 'hello  world' | tr -s ' '`  
  **Output**: `hello world`

#### Character Classes

- Use predefined classes (e.g., alnum, digit, blank).  
  **Example**: `echo 'Hello World!' | tr -d '[:punct:]'`  
  **Output**: `Hello World`

#### Combining with Other Commands

- Delete non-numeric characters in a string.  
  **Example**: `echo 'Price: 25$' | tr -cd '[:digit:]'`  
  **Output**: `25`

- Replace newlines with spaces.  
  **Example**: `echo -e 'hello\nworld' | tr '\n' ' '`  
  **Output**: `hello world`

#### Flags

- `-c`: Complements the set of characters specified for translation or deletion.
- `-d`: Removes the specified characters from the input.
- `-s`: Replaces each sequence of repeated characters with a single occurrence.
- `-t`: Truncates the first set of characters to match the length of the second set before processing.

#### Predefined Character Classes

These are special sets of characters that you can use with `tr`. They are handy for a range of common tasks like removing all digits or converting text to upper or lower case.

- `[:alnum:]`: Alphanumeric characters (`a-z`, `A-Z`, `0-9`).
- `[:alpha:]`: Alphabetic characters (`a-z`, `A-Z`).
- `[:blank:]`: Space and tab.
- `[:cntrl:]`: Control characters.
- `[:digit:]`: Numerical digits (`0-9`).
- `[:graph:]`: Visible characters (`a-z`, `A-Z`, `0-9`, and symbols).
- `[:lower:]`: Lowercase letters (`a-z`).
- `[:print:]`: Visible characters and spaces.
- `[:punct:]`: Punctuation characters.
- `[:space:]`: Whitespace characters (space, newline, tab, etc).
- `[:upper:]`: Uppercase letters (`A-Z`).
- `[:xdigit:]`: Hexadecimal digits (`0-9`, `a-f`, `A-F`).
