### Linux `uniq` and `sort` Commands Cheat Sheet

#### `uniq` Command

- Remove duplicate lines from sorted input.  
`sort file.txt | uniq`

- Count occurrences of each line.  
`sort file.txt | uniq -c`

- Show only duplicated lines.  
`sort file.txt | uniq -d`

- Show only unique lines.  
`sort file.txt | uniq -u`

#### `sort` Command

- Sort lines in text file.  
`sort file.txt`

- Sort in reverse order.  
`sort -r file.txt`

- Sort by numerical value.  
`sort -n numbers.txt`

- Sort by month name.  
`sort -M months.txt`

- Sort and remove duplicates.  
`sort -u file.txt`

#### Combining `uniq` and `sort`

- Sort and then remove duplicates.  
`sort file.txt | uniq`

- Count and sort lines by occurrences.  
`sort file.txt | uniq -c | sort -n`

- Sort by month and remove duplicates.  
`sort -M months.txt | uniq`
