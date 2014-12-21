# multitasker

`multitasker` is a utility for executing commands in multiple directories.

## Installation

`npm -g install multitasker`

## Usage

`multitasker` keeps track of directories via tags (stored in `~/.multitasker.conf`). Tagging directories is easy:

```bash
$ multitasker tag work # if no directories are provided, the current directory is used
$ multitasker tag work ~/work/client ~/work/server # or you can specify directories
```

Then, execute commands via `multitasker exec`:

```bash
$ multitasker exec work git pull # runs "git pull" in all directories tagged "work"
```

You can view your tagged directories via `multitasker tags` and un-tag directories using `multitasker untag`.

For more options, run `multitasker -h` or `multitasker <subcommand> h-`.
