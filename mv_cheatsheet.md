### `mv` Command Cheat Sheet

| Option | Description | Example |
|---------|--------------|----------|
| `mv` | Basic move or rename | `mv file1.txt /home/user/docs/` |
| `-i` | Prompt before overwriting existing files | `mv -i file1.txt /path/` |
| `-u` | Move only if the source file is newer | `mv -u file1.txt /path/` |
| `-v` | Verbose mode (show details of the move operation) | `mv -v file1.txt /path/` |
| `-f` | Force overwrite without confirmation | `mv -f file1.txt /path/` |
| `--backup` | Create a backup of the destination file if it exists | `mv --backup file1.txt /path/` |
| `--no-clobber` | Do not overwrite any existing files | `mv --no-clobber file1.txt /path/` |
| `mv /dir/ /path/` | Move a directory and all its contents to a new location | `mv /source/dir /home/user/newlocation/` |
| `mv file1 newfile` | Rename a file | `mv file1.txt newfile.txt` |