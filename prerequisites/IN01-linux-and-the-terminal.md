# IN01. Linux and the terminal

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Programming | 1. Foundations | none | IN02, IN03, IN05, SY05 |

## Why this module

Every tool of the project runs from a terminal: compilers, the Python interpreter, Git, training runs that last hours, GPU monitoring, remote machines reached over SSH. Being fast and safe in a shell is the ground floor of all the engineering that follows.

## Objectives

After this module, you can navigate and manage files, chain commands, write small bash scripts, inspect and control processes, manage permissions and environment variables, install software and work on a remote machine over SSH.

## Competences evaluated

1. Navigate the file system with absolute and relative paths; explain the standard directories (`/home`, `/etc`, `/usr`, `/tmp`, `/proc`, `/dev`).
2. Create, copy, move, rename, delete and search files and directories (`ls`, `cp`, `mv`, `rm`, `mkdir`, `find`), safely.
3. Read and change permissions and ownership (`chmod` in symbolic and octal form, `chown`), and explain what execute permission means on a directory.
4. Use redirections (`>`, `>>`, `<`, `2>`, `2>&1`) and pipes, and combine text tools (`cat`, `less`, `head`, `tail`, `grep`, `sort`, `uniq`, `wc`, `cut`, `sed`, `awk` basics, `xargs`).
5. Use quoting and expansions correctly (single and double quotes, variables, globs, command substitution).
6. Write bash scripts with variables, arguments, conditions, loops, functions and exit codes, and make them fail on errors (`set -euo pipefail`).
7. Set, export and inspect environment variables; explain `PATH` and how a command is found.
8. Inspect and control processes: list them (`ps`, `top`), send signals (`kill`, Ctrl-C, Ctrl-Z), run jobs in the background, keep a command running after logout, and read exit codes.
9. Inspect resources: disk usage (`df`, `du`), memory (`free`), GPU (`nvidia-smi`), and limit a command's memory and priority (`nice`, `systemd-run`).
10. Install and update software with the package manager, and explain what a package and a dependency are.
11. Connect to a remote machine with SSH keys, copy files (`scp`, `rsync`) and keep a session alive (`tmux`).
12. Edit files in a terminal editor (vim or nano) and read manual pages (`man`, `--help`).

## Notions, in learning order

1. **What an operating system and a shell are**: kernel, user space, terminal, shell, prompt.
2. **The file system**: tree, root, home, paths, hidden files, links (hard and symbolic).
3. **Managing files**: the basic commands, wildcards, the danger of `rm -rf` and how to protect against it.
4. **Permissions**: users, groups, read, write and execute bits, `sudo`, ownership.
5. **Text and streams**: standard input, output and error, redirections, pipes, the text toolbox.
6. **Shell language**: variables, quoting, expansions, command substitution, arithmetic.
7. **Scripts**: shebang, arguments, conditions (`test`, `[[ ]]`), loops, functions, exit codes, strict mode, debugging (`bash -x`).
8. **Environment**: environment variables, `PATH`, shell configuration files.
9. **Processes**: process identifiers, parent and children, signals, jobs, background and foreground, `nohup`, `tmux`.
10. **Resources and limits**: disk, memory, CPU, GPU monitoring, priorities, memory limits with cgroups through `systemd-run`.
11. **Software installation**: package managers (`apt`), repositories, building from source (`./configure && make` in principle).
12. **Remote work**: SSH, key pairs, `~/.ssh/config`, copying files, port forwarding.
13. **Editors and documentation**: vim basics (modes, save, quit, search, replace), `man` pages.

## Practice

- Daily terminal use for everything (no file manager) for the duration of the module.
- Scripts of increasing size: a backup script, a log analyzer (top errors of a file with pipes), a script that runs a command under a memory limit and logs its output and duration.
- A treasure hunt in a prepared directory tree using only `find`, `grep` and pipes.

## Evaluation format

One practical session at the terminal, about 2 hours: around 15 tasks to perform (file operations, pipelines, permissions, processes, resources), 2 scripts to write and run, and short explanation questions. Pass mark 100 %.

## References

- MIT, *The Missing Semester of Your CS Education* (free lectures and notes): shell, scripting, editors, command-line environment, remote machines.
- William Shotts, *The Linux Command Line* (free book).
- `man bash`, and the GNU Bash manual (free).
