### Linux `base64` Command Cheat Sheet

#### TL;DR on Base64 Encoding

Base64 encoding is a binary-to-text encoding scheme that converts binary data to an ASCII string format. It's commonly used to encode data that may otherwise cause issues when transferred or stored, such as in emails and URL tokens.

**Example:** Encoding the string 'Hello, World!' to Base64 yields 'SGVsbG8sIFdvcmxkIQo=='.

Common Uses:

- Embedding images in HTML or CSS.
- Encoding email attachments.
- Generating URL-safe tokens.
- Storing complex data in JSON strings.

#### Basic Command Usage

- Encode a file to Base64.
`base64 file.txt > encoded.txt`

- Decode a Base64 file.
`base64 -d encoded.txt > file.txt`

#### Input and Output

- Encode from standard input.
`echo 'Hello' | base64`

- Decode to standard output.
`echo 'SGVsbG8=' | base64 -d`

#### Wrapping Options

- Disable line wrapping (default is 76 characters).
`base64 -w 0 file.txt`

- Set wrap length to N characters.
`base64 -w N file.txt`

#### Ignoring Garbage

- Ignore non-alphabet characters (useful for decoding).
`base64 -i -d encoded_with_garbage.txt > file.txt`

#### Combining with Other Commands

- Pipe content to encode.
`cat file.txt | base64`

- Pipe content to decode.
`echo 'SGVsbG8=' | base64 -d`
