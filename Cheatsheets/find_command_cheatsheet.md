### Linux `find` Command Cheat Sheet

#### Basic Usage

- Find files by name.  
`find /path/to/dir -name "filename"`

- Find directories by name.  
`find /path/to/dir -type d -name "dirname"`

#### Search Depth

- Limit search depth to specific levels.  
`find /path/to/dir -maxdepth 2 -name "filename"`

- Start search from specific depth.  
`find /path/to/dir -mindepth 2 -name "filename"`

#### Time-based Search

- Find files modified within last N days.  
`find /path/to/dir -mtime -N`

- Find files accessed within last N hours.  
`find /path/to/dir -amin -N`

#### Size-based Search

- Find files larger than N bytes.  
`find /path/to/dir -size +Nc`

- Find files smaller than N bytes.  
`find /path/to/dir -size -Nc`

#### File Permissions and Ownership

- Find files with specific permissions.  
`find /path/to/dir -perm 0644`

- Find files owned by user.  
`find /path/to/dir -user username`

#### Combining Conditions

- Combine multiple conditions using `and` (`-a`).  
`find /path/to/dir -name "*.txt" -a -size +2k`

- Combine multiple conditions using `or` (`-o`).  
`find /path/to/dir -name "*.txt" -o -name "*.md"`

#### Executing Commands on Found Files

- Find all .txt files in the specified directory and its subdirectories and delete them:
`find /path/to/dir -name "*.txt" -exec rm {} \;`
