# Linux Piping and Redirection Cheat Sheet

#### Piping (`|`)

- Send output of one command as input to another.  
  `ls -l | grep '.txt'`

#### Redirecting to a File (`>` and `>>`)

- **Overwrite (`>`)**: Redirect output to a file, overwrite file.  
  `echo "Hello World" > hello.txt`

- **Append (`>>`)**: Redirect output to a file, append to file.  
  `echo "Hello again" >> hello.txt`

#### Redirecting Input (`<`)

- Take a file as input to a command.  
  `sort < unsorted.txt`

#### Redirecting Standard Error (`2>` and `2>>`)

- **Overwrite (`2>`)**: Redirect standard error to a file, overwrite file.  
  `find / -name "*.txt" 2> errors.txt`

- **Append (`2>>`)**: Redirect standard error to a file, append to file.  
  `find / -name "*.txt" 2>> errors.txt`

#### Redirecting Both Output and Error (`&>` and `&>>`)

- **Overwrite (`&>`)**: Redirect both output and error to a file, overwrite it.  
  `ls /fake/directory &> output_and_errors.txt`

- **Append (`&>>`)**: Redirect both output and error to a file, append to it.  
  `ls /fake/directory &>> output_and_errors.txt`

#### Combining Piping and Redirection

- Combine for complex operations.  
  `ls -l | grep ".txt" > txt_files.txt`
