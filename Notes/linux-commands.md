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

# Comprehensive Guide to Using `find` on Ubuntu

The `find` command in Linux is a powerful tool to search for files and directories based on various criteria like name, type, size, modification date, and content. This guide covers the basics and advanced usage with practical examples.

---


# Comprehensive Guide to Using `find` on Ubuntu

The `find` command in Linux is a powerful tool to search for files and directories based on various criteria like name, type, size, modification date, permissions, ownership, and content. This guide covers basic and advanced usage with practical examples.

---

## 1️⃣ Basic Syntax

```bash
find [path] [options] [expression]
```
- `path` → directory to start searching (e.g., `.` for current, `~` for home)  
- `options` → filters like file type, size, permissions  
- `expression` → conditions like name, regex, ownership  

---

## 2️⃣ Search by Filename

- Exact filename:

```bash
find . -type f -name "example.txt"
```

- Case-insensitive:

```bash
find . -type f -iname "example.txt"
```

- Pattern matching:

```bash
find . -type f -name "*.pdf"
find . -type f -iname "*python*.pdf"
```

---

## 3️⃣ Search by File Type

- Files only:

```bash
find . -type f
```

- Directories only:

```bash
find . -type d
```

- Symbolic links:

```bash
find . -type l
```

- Socket files:

```bash
find . -type s
```

- Named pipes (FIFO):

```bash
find . -type p
```

---

## 4️⃣ Search by Size

- Files larger than 10 MB:

```bash
find . -type f -size +10M
```

- Files smaller than 1 MB:

```bash
find . -type f -size -1M
```

- Files exactly 512 KB:

```bash
find . -type f -size 512k
```

---

## 5️⃣ Search by Modification, Access, and Change Time

- Modified in last 7 days:

```bash
find . -type f -mtime -7
```

- Accessed in last 2 days:

```bash
find . -type f -atime -2
```

- Metadata changed more than 30 days ago:

```bash
find . -type f -ctime +30
```

- Modified within last N minutes:

```bash
find . -type f -mmin -60
```

---

## 6️⃣ Search by Permissions

- Files readable by owner:

```bash
find . -type f -perm u+r
```

- Files writable by group:

```bash
find . -type f -perm g+w
```

- Files executable by all:

```bash
find . -type f -perm a+x
```

- Exact permission match:

```bash
find . -type f -perm 644
```

---

## 7️⃣ Search by Ownership

- Files owned by a user:

```bash
find . -type f -user username
```

- Files owned by a group:

```bash
find . -type f -group groupname
```

---

## 8️⃣ Search by Depth

- Only current directory:

```bash
find . -maxdepth 1 -type f
```

- Minimum depth 2:

```bash
find . -mindepth 2 -type f
```

---

## 9️⃣ Search by Name and Execute Actions

- Delete all `.tmp` files:

```bash
find . -type f -name "*.tmp" -exec rm -f {} \;
```

- Move `.txt` files to another folder:

```bash
find . -type f -name "*.txt" -exec mv {} ~/Documents/text_files/ \;
```

- List files with detailed info:

```bash
find . -type f -exec ls -lh {} \;
```

---

## 🔟 Search by Content (PDF Example)

```bash
sudo apt install pdfgrep
pdfgrep -i "python" *.pdf
```

---

## 1️⃣1️⃣ Search in Entire System

```bash
sudo find / -type f -iname "*python*.pdf" 2>/dev/null
```

---

## 1️⃣2️⃣ Combine Conditions

- Find `.log` files larger than 5 MB:

```bash
find . -type f -name "*.log" -size +5M
```

- Find files modified in last 7 days and owned by a user:

```bash
find . -type f -mtime -7 -user username
```

- Find directories not accessed in 30 days:

```bash
find . -type d -atime +30
```

---

## 1️⃣3️⃣ Useful Tips

- Test commands without `-exec` first.  
- Quote patterns to prevent shell expansion.  
- Combine `find` with `grep` for extra filtering.  
- Use `-print` explicitly if needed:

```bash
find . -type f -name "*.txt" -print
```

---

## 1️⃣4️⃣ Quick Example: Finding Python PDFs

```bash
# Search in home directory
find ~/ -type f -iname "*python*.pdf"

# Search entire system
sudo find / -type f -iname "*python*.pdf" 2>/dev/null

# Search by content inside PDFs
pdfgrep -i "python" ~/Documents/*.pdf
```

---

