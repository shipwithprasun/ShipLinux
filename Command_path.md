## Cheatsheet: Command Path Basics

- **View current PATH**  
  `echo $PATH`  
  Displays the list of directories Linux checks for commands.

- **Find command location**  
  `which <command>`  
  Shows the path to the executable for a given command—useful for debugging script execution issues.

- **Temporarily add directory to PATH**  
  `export PATH="/path/to/dir:$PATH"`  
  Changes last only for the current session; used in temporary debugging or automation scripts.

- **Permanently add directory to PATH**  
  Edit `~/.bashrc` and add:  
  `export PATH="/path/to/dir:$PATH"`  
  Then apply changes with:  
  `source ~/.bashrc`  
  Ensures custom tools/scripts are always available.

- **Remove directory from PATH**  
  Edit `~/.bashrc` for user changes or `/etc/environment` for system-wide changes, and update the PATH line.

## DevOps & Automation Use Cases

### Script Portability
Automate inclusion of custom tools by adding their directory to PATH at the start of scripts:
  - Example: In CI/CD pipelines or cron jobs, use `export PATH="/opt/build_tools:$PATH"` to ensure build tools are discoverable without specifying full paths.

### Environment Customization
Customize developer environments for consistent deployments:
  - Add custom binaries or scripts to PATH in configuration scripts, so all developers or servers have the same CLI utilities available.

### Security & Access Control
Control exposure of executables by modifying PATH:
  - Remove sensitive directories from PATH in production or automation scripts to reduce accidental execution of non-standard binaries.

### Troubleshooting and Automation
Quickly find out which executable will run (`which <command>`), especially in environments where tools might be duplicated or overridden by custom installs.
