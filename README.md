# multitasker

`multitasker` is a utility for executing commands in multiple directories.

## Installation

`npm -g install multitasker`

## Usage

`multitasker` keeps track of directories via tags you define. Commands can then be executed in the tagged directories.

### Managing tags

Tagging directories is easy:

```bash
$ multitasker tag work # if no directories are provided, the current directory is used
$ multitasker tag work ~/work/client ~/work/server # or you can specify directories
```

You can view your tagged directories via `multitasker tags` and un-tag directories using `multitasker untag`. Tags are stored in `~/.multitasker.conf`.

### Executing commands

Commands are executed via `multitasker exec`:

```bash
$ multitasker exec work git pull # runs "git pull" in all directories tagged "work"
```

By default, the commands are executed in each directory simultaneously. If desired, a max number of concurrent executions can be defined with the `-m` or `--max` flag. For example, this may be useful for commands that involve SSH connections (like `git pull`), for which there is a limit of simultaneous connections for a given machine.

Commands can also be run sequentially in each tagged directory, with the `-s` or `--serial` flag. This may be useful for memory- or CPU-intensive processes.

### Help and options

For more options, run `multitasker -h` or `multitasker <subcommand> h-`.
