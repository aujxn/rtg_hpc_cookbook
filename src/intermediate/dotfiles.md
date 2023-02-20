# Dotfiles and Environment Variables

## ENV VARS

Environment variables are commonly used to communicate
certain information to other programs and allow a simple
way to make systemic environment changes. These are simple
key-value pairs stored by the shell, where a string
identifier is paired with a string value.

Typically, these variables are SCREAMING_CASE. An environment
variable can be set in your current shell with the export command:

```bash
export MY_VARIABLE=cat
```

This is not shared with other running shells. All variables are
passed to any processes started from this shell.

A variable can be referenced in a shell script or command with
the `$`.

```bash
echo $MY_VARIABLE
```

Will print `cat` to the terminal. Many variables are set by
default such as `$HOME` which contains the path to your home
directory. Variables are useful for saving long paths and
passing configuration information to certain programs.

Three of the most critical environment variables are:

- `PATH` only binaries found in directories listed here are
found by the shell when executing. To determine if a binary
is in your path try `which <program_name>`
- `PYTHONPATH` tells python where to look for modules
- `LD_LIBRARY_PATH` tells binaries and compilers where to
find shared objects

All three of these are `:` separated lists of paths.
Accidental destruction of any of these can break lots of
things. Exit out of the session and `ssh` back in to restore
these variables.

Many errors are because these values are not properly configured.

Example --- to add a directory to your `PATH`:
```bash
export PATH=$HOME/bin:$PATH
```

## Dotfiles

Dotfiles are configuration files that are usually found in
`$HOME` or `$HOME/.config/`. The preceding `.` in the filename
or directory hides the file by default. To show these hidden
files `ls -a` will list all files in the current directory.

The most basic dotfile is the `.bashrc`.
The Bash script in this file is run when a new shell is
initiated. Generally, this is where you can set environment
variables, custom shell functions, command aliases, and
other environment set up like virtualization layers.

Other software with custom configuration can have its own
dotfiles. In the Configuring Vim chapter, I show how you
can edit your `.vimrc` to customize Vim.
