# Linux Environment Variables Cheatsheet

## Common Environment Variables

| Variable         | Purpose                                      |
|------------------|----------------------------------------------|
| `$HOME`          | Home directory of current user               |
| `$USER`          | Username of current user                     |
| `$PATH`          | Search path for executables                  |
| `$PWD`           | Present working directory                    |
| `$SHELL`         | Default shell                                |
| `$EDITOR`        | Default text editor                          |
| `$LANG`          | System language/locale                       |
| `$HOSTNAME`      | Computer's hostname                          |

## Basic Commands

| Command                              | Description                                             |
|---------------------------------------|--------------------------------------------------------|
| `echo $VAR`                          | Print value of VAR                                     |
| `env`                                | Show all environment variables                         |
| `printenv`                           | Show environment variables (and specific VARs)          |
| `export VAR=value`                    | Set environment variable VAR                           |
| `unset VAR`                          | Remove variable                                        |
| `export VAR=$VAR:newval`             | Add to variable value (often for PATH, etc.)           |

## Example Usages

```
export PATH="/usr/local/bin:$PATH"          # Prepend directory to PATH
export EDITOR="vim"                         # Set default text editor
unset EDITOR                                # Unset EDITOR variable
echo $PATH                                  # Print PATH variable
printenv USER                               # Print current username
```

## Tips

- Variable names are case-sensitive. Usually uppercase by convention.
- Use `:` for separating multiple values (e.g. in PATH).
- Use `export` to make a variable available in subshells.
- Changes made in a terminal session are temporary. To make them permanent, add export statements to `~/.bashrc` or `~/.profile`.