# Unix/Linux Commands Documentation

## Table of Contents
1. [pwd](#pwd)
2. [touch](#touch)
3. [rm -f](#rm-f)
4. [ln](#ln)
5. [cat](#cat)
6. [rmdir](#rmdir)
7. [tail](#tail)
8. [vi](#vi)
9. [man](#man)
10. [groupmod](#groupmod)

---

## pwd
The `pwd` command stands for "print working directory." It displays the full path of the current working directory.

### Usage
```sh
pwd
```

### Example
```sh
$ pwd
/home/user
```

---

## touch
The `touch` command is used to update the access and modification times of files. If the file does not exist, `touch` creates an empty file.

### Usage
```sh
touch [options] file...
```

### Options
- **`-a`**: Change only the access time.
- **`-m`**: Change only the modification time.
- **`-t`**: Use the specified timestamp.

### Example
```sh
touch newfile.txt
```

---

## rm -f
The `rm` command is used to remove files or directories. The `-f` option forces the removal without prompting for confirmation.

### Usage
```sh
rm -f file
```

### Example
```sh
rm -f myfile.txt
```

---

## ln
The `ln` command is used to create links between files. By default, it creates hard links. The `-s` option creates symbolic (soft) links.

### Usage
```sh
ln [options] target link_name
```

### Options
- **`-s`**: Create a symbolic link.

### Example
```sh
ln -s /path/to/file linkname
```

---

## cat
The `cat` command concatenates and displays the contents of files.

### Usage
```sh
cat [options] file...
```

### Options
- **`-n`**: Number all output lines.
- **`-b`**: Number non-blank output lines.

### Example
```sh
cat file1.txt file2.txt
```

---

## rmdir
The `rmdir` command removes empty directories.

### Usage
```sh
rmdir [options] directory
```

### Options
- **`--ignore-fail-on-non-empty`**: Ignore each failure that is solely because a directory is non-empty.
- **`-p, --parents`**: Remove directory and its ancestors.

### Example
```sh
rmdir mydirectory
```

---

## tail
The `tail` command displays the last part of files.

### Usage
```sh
tail [options] [file...]
```

### Options
- **`-n`**: Number of lines to display.

### Example
```sh
tail -n 10 logfile.txt
```

---

## vi
`vi` is a text editor available in Unix-like operating systems.

### Basic Usage
To open a file with `vi`:
```sh
vi filename
```
### Modes in `vi`
1. **Normal Mode**: Navigate the file and perform operations.
2. **Insert Mode**: Insert and edit text.

### Basic Commands
- **Switching to Insert Mode**:
  - `i`: Insert before the cursor.
  - `a`: Insert after the cursor.
  - `o`: Open a new line below.
  
- **Saving and Exiting**:
  - `:w`: Save the file.
  - `:q`: Quit `vi`.
  - `:wq`: Save and quit.
  - `:q!`: Quit without saving.

- **Navigating**:
  - `h`: Move left.
  - `j`: Move down.
  - `k`: Move up.
  - `l`: Move right.

- **Deleting Text**:
  - `x`: Delete character under the cursor.
  - `dd`: Delete the current line.

- **Undo and Redo**:
  - `u`: Undo the last change.
  - `Ctrl-r`: Redo the undone change.

### Example Workflow
1. **Open a file**:
   ```sh
   vi myfile.txt
   ```

2. **Enter Insert Mode**:
   - Press `i`.

3. **Save the file**:
   - Press `Esc`.
   - Type `:w` and press `Enter`.

4. **Quit `vi`**:
   - Type `:q` and press `Enter`.

5. **Save and Quit**:
   - Type `:wq` and press `Enter`.

6. **Quit without Saving**:
   - Type `:q!` and press `Enter`.

### Advanced Features
- **Copying and Pasting**:
  - `yy`: Yank (copy) the current line.
  - `p`: Paste after the cursor.

- **Search and Replace**:
  - `/pattern`: Search for `pattern`.
  - `:%s/old/new/g`: Replace all occurrences.

---

## man
The `man` command displays the manual pages for commands, utilities, and functions.

### Usage
```sh
man command_name
```

### Structure of a Man Page
1. **NAME**: Name and brief description.
2. **SYNOPSIS**: Syntax and usage.
3. **DESCRIPTION**: Detailed description.
4. **OPTIONS**: List of options and arguments.
5. **EXAMPLES**: Usage examples.
6. **SEE ALSO**: Related commands.

### Navigating Man Pages
- **Scroll Down**: Press `Down Arrow` or `Enter`.
- **Scroll Up**: Press `Up Arrow`.
- **Next Page**: Press `Space`.
- **Previous Page**: Press `b`.
- **Search**: Press `/` followed by the search term.
- **Quit**: Press `q`.

### Examples
1. **View the manual page for `ls`**:
   ```sh
   man ls
   ```

2. **Search for a keyword**:
   ```sh
   man -k copy
   ```

3. **Short description of a command**:
   ```sh
   man -f tar
   ```

---

## groupmod
The `groupmod` command modifies a group’s definition.

### Usage
```sh
groupmod [options] group
```

### Options
- **`-g, --gid GID`**: Change the group ID.
  ```sh
  groupmod -g 1001 group_name
  ```

- **`-n, --new-name NEW_GROUP`**: Rename the group.
  ```sh
  groupmod -n new_group_name old_group_name
  ```

- **`-h, --help`**: Display help information.
  ```sh
  groupmod -h
  ```

### Examples
1. **Change the GID of a Group**:
   ```sh
   groupmod -g 1002 developers
   ```

2. **Rename a Group**:
   ```sh
   groupmod -n devs developers
   ```

### Important Notes
- **Superuser Privileges**: Modifying groups requires superuser (root) privileges. Use `sudo` if necessary.
  ```sh
  sudo groupmod -g 1002 developers
  ```

- **Consistency**: Ensure that files using the old GID are updated to the new GID.

- **User Sessions**: Changes take effect immediately, but logged-in users may need to log out and back in.

---
