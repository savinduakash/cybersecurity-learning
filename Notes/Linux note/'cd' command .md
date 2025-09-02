# Linux `cd` Command - Complete Learning Package

## 1. All Options

| Option | Description |
|--------|-------------|
| `-L`   | Follow symbolic links (default behavior). |
| `-P`   | Use the physical directory structure without following symbolic links. |
| `-e`   | If used with `-P`, causes `cd` to return an unsuccessful status if the current working directory cannot be determined after a successful directory change. |
| `-`    | Change to the previous directory. Equivalent to `$OLDPWD`. |
| `directory` | The target directory to change to. If not specified, defaults to the value of the `HOME` environment variable. |

## 2. Examples for Each Option

### `cd -L`
```bash
cd -L /path/to/directory
```
Follows symbolic links.

### `cd -P`
```bash
cd -P /path/to/directory
```
Uses physical directory structure.

### `cd -e`
```bash
cd -P -e /path/to/directory
```
Returns unsuccessful status if current directory cannot be determined.

### `cd -`
```bash
cd -
```
Changes to the previous directory.

### `cd directory`
```bash
cd /path/to/directory
```
Changes to the specified directory or `$HOME` if none specified.

## 3. Step-by-Step Lab Worksheet

### a) Setup
```bash
mkdir -p ~/testdir/subdir1/subdir2
ln -s ~/testdir/subdir1 ~/testlink
cd ~
```

### b) Command-Line Options Practice
```bash
cd -L ~/testlink
cd -P ~/testlink
cd -
cd ~/testdir/subdir1/subdir2
```

### c) Interactive Mode Practice
```bash
cd ~/testdir
cd subdir1
cd subdir2
cd -
```

### d) Cleanup
```bash
rm -rf ~/testdir
rm ~/testlink
```


- [Bash Manual: cd](https://www.gnu.org/software/bash/manual/html_node/The-Set-Builtin.html)
- [Linux Command Library: cd](https://linuxcommandlibrary.com/man/cd)
