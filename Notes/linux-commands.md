# Basic Linux Commands for Cybersecurity

| Command | Description |
|---------|-------------|
| ls      | List files and directories |
| cd      | Change directory |
| pwd     | Print working directory |
| mkdir   | Make new directory |
| rm      | Remove files or directories |
| chmod   | Change file permissions |
| sudo    | Run command as root |
| ufw     | Manage firewall rules |
| netstat | Show network connections |
| ssh     | Connect to remote server |

## Search files in Ubuntu terminal

The two primary tools to use search files in ubuntu terminal.<br>
1.search<br>
...The find command is highly flexible and allows you to search based on various conditions such as file name, directory, modification date, size, and permissions. For example, to search for a file named "softwares" in the current directory, use find . -iname Softwares.
 To search for files modified within the last two days, use find . -mtime -2.
 For files larger than 5MB, use find . -size +5M.
 To search for directories specifically, use the -type d flag, such as find /user -name "sdk" -type d for case-sensitive searches or find /user -iname "sdk" -type d for case-insensitive ones.

