# Nano Text Editor Cheat Sheet

## Check if nano is installed prior

### Check for output like:

### Code:

```sh
sudo apt list|grep -w nano
```
### Output:
```
nano/noble-updates,noble-security,now 7.2-2ubuntu0.1 amd64 [installed,automatic]
```
## Installing nano
```sh
sudo apt/yum/dnf install nano
```

## Essential Shortcuts

| Key / Shortcut     | Description                                     |
|--------------------|-------------------------------------------------|
| `nano filename`    | Open or create a file for editing               |
| `Ctrl+O`           | Write (save) changes to file                    |
| `Ctrl+X`           | Exit Nano (prompts to save if modified)         |
| `Ctrl+G`           | Display help                                    |
| `Ctrl+K`           | Cut entire line or selected text                |
| `Ctrl+U`           | Paste previously cut/copied text                |
| `Ctrl+6`           | Set/cancel a text selection marker              |
| `Alt+6`            | Copy selected text                              |
| `Ctrl+A`           | Move to start of current line                   |
| `Ctrl+E`           | Move to end of current line                     |
| `Ctrl+Y` / `Ctrl+V`| Scroll up/down one page                         |
| `Ctrl+W`           | Search                                          |
| `Ctrl+\`           | Search and replace                              |
| `Alt+U` / `Alt+E`  | Undo/redo last action                           |
| `Ctrl+_`           | Go to line/column                               |

## DevOps Best Practices & Examples

### Open a Config File with Line Number
```sh
nano +25 /etc/nginx/nginx.conf   # Opens file at line 25
```

### Edit System Files with Sudo (for permissions)
```sh
sudo nano /etc/hosts
```

### Quick Edit (No Prompts) — Dangerous!
```sh
nano --tempfile myscript.sh      # Exits without save prompt
```

### Backup Before Edit
```sh
nano -B myconfig.yaml            # Creates myconfig.yaml~ backup
```

### Automatic Indentation for Scripts
```sh
nano -I script.sh
```

### Syntax Highlighting
```sh
nano -Y sh script.sh
```

## Power User Configuration Tips (`~/.nanorc`)

Add the following in your `~/.nanorc` for a better experience:

```nanorc
set linenumbers      # Show line numbers
set autoindent       # Indent new lines automatically
set backup           # Create file backups on write
set softwrap         # Word-wrap long lines instead of scrolling
set mouse            # Enable mouse support
```

**Note:** Syntax highlighting rules can be included for various languages—see Nano documentation for details.[3][5]

## DevOps Usage Scenarios

- **Editing server configuration**: Use line numbers and backup to prevent errors while updating critical configs.
- **Working on scripts**: Enable autoindent and syntax highlighting for shell, YAML, Python, etc.
- **Quick fix on production**: Use `sudo`, ensure you work on a backup copy, and know how to undo changes.
- **Log file review and edits**: Nano can handle large log files; use `Ctrl+_` to jump to the line showing an error.

## Important Tips & Cautions

- **Saving**: `Ctrl+O` saves your file—make it a habit to save early and often.
- **Exiting**: `Ctrl+X` exits; never panic if changes need saving, as you'll be prompted.[2]
- **Permissions**: If you see a "Permission denied" error when saving, you'll need elevated rights (e.g., `sudo`).[2]
- **Copy/Cut vs. Clipboard**: Nano’s shortcuts (`Alt+6`, `Ctrl+K`, `Ctrl+U`) are internal—they don’t touch your system clipboard. Use `Ctrl+Shift+C/V` (in terminal) for standard clipboard instead.[1]
- **Avoid Forgotten Prompts**: The `--tempfile` flag disables exit prompts—use cautiously, especially for critical files.[5]
- **Restore with Backup**: If things go wrong, `.bak` or `~` files (when `-B` or `set backup` is used) provide quick restores.[5][2]
- **Disable Help Bar**: For more space, add `set nohelp` in `.nanorc`, but only if you're confident with shortcuts.[5]

## Frequently Used Flags for DevOps

| Flag      | Description                  | Example                         |
|-----------|------------------------------|---------------------------------|
| `-B`      | Backup before save           | `nano -B /etc/fstab`            |
| `-I`      | Auto-indent                  | `nano -I script.py`             |
| `-Y`      | Syntax highlighting          | `nano -Y yaml playbook.yml`     |
| `-c`      | Show cursor position         | `nano -c config.conf`           |
| `-m`      | Enable mouse support         | `nano -m hosts`                 |

## Troubleshooting

- **Terminal Frozen with `Ctrl+S`**: If you hit `Ctrl+S` accidentally, unfreeze with `Ctrl+Q`.[1]
- **Read-only Mode**: Use `sudo` or fix permissions as needed.
- **Line Endings**: For DevOps, prevent unexpected changes to config files by controlling newlines in `.nanorc` using `set nonewlines`.[5]

## Further Reading

- [Nano Official Cheatsheet][3]
- [Its FOSS Nano Guide][1]
- [Nano Usage & Flags][6][2]

***

**Remember:** Nano is simple, but very flexible practice core shortcuts, use backups and configuration wisely, and customize it for your daily DevOps workflow for maximum efficiencyncy!

[1](https://itsfoss.com/nano-editor-guide/)
[2](https://ioflood.com/blog/nano-linux-command/)
[3](https://www.nano-editor.org/dist/latest/cheatsheet.html)
[4](https://www.geeksforgeeks.org/linux-unix/linux-commands-cheat-sheet/)
[5](https://timnash.co.uk/customising-nano-productivity-friday/)
[6](https://phoenixnap.com/kb/use-nano-text-editor-commands-linux)
[7](https://www.interserver.net/tips/kb/how-to-efficiently-use-nano-text-editor-in-ubuntu-linux-os/)
[8](https://blog.devops.dev/linux-commands-cheatsheet-cac3c70845e2)
[9](https://www.scribd.com/document/890927585/DevOps-Cheat-Sheet-Updated)
[10](https://www.linkedin.com/posts/amankc-neo_linux-commands-cheat-sheet-beginner-to-advanced-activity-7237359776249057283-Irls)
[11](https://www.nano-editor.org/dist/v3/nano.html)
[12](https://github.com/girishkumarkh/devops-cheatsheet)
[13](https://www.youtube.com/watch?v=PDWHxh9HUF8)
[14](https://www.edureka.co/blog/cheatsheets/ansible-cheat-sheet-guide/)
[15](https://www.hostafrica.com/blog/linux/beginners-guide-to-gnu-nano-text-editor-linux/)
[16](https://linuxize.com/post/how-to-use-nano-text-editor/)
[17](https://www.reddit.com/r/linux/comments/esw4in/does_anyone_else_enjoy_using_nano_for_a_terminal/)
[18](https://www.tecmint.com/learn-nano-text-editor-in-linux/)
[19](https://blog.smittytone.net/2020/06/19/spruce-up-the-nano-text-editor-with-syntax-colouring-and-more/)
[20](https://help.ubuntu.com/community/Nano)
[21](https://www.agnosticdev.com/content/configure-nano-command-line-development)