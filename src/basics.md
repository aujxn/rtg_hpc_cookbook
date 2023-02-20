# Basics

This chapter covers the basics of working in a remote linux server
targeted at someone with little to no experience working with
command line interfaces.

Code blocks are almost always commands you will enter into the
terminal unless specified otherwise.

## Login with `ssh`

The address for logging into the Research Computing (RC) servers
is shown below. Replace `<odin>` with your odin username (this
`<...>` pattern is used often in this guide and in the Linux `man` pages).

The login nodes are only accessible directly by devices that are
on the PSU Secure WiFi network. To login to these resources from
off campus, you will either need to configure the OIT provided
VPN or first `ssh` into `rc.pdx.edu` --- more on that later.

This Linux tool `ssh` is short for secure shell. It provides you
an encrypted connection to the RC compute resources and is a
ubiquitous Linux tool. Here are the basics commands to get started:

```bash
ssh <odin>@login2.coeus.rc.pdx.edu
```

OIT strongly prefers you set up password-less login using an SSH key,
learn how to set that up here:
- [Linux or Mac](https://www.tecmint.com/ssh-passwordless-login-using-ssh-keygen-in-5-easy-steps/)
- [Windows with PuTTY](https://www.tecmint.com/ssh-passwordless-login-with-putty/)

If you require port forwarding (for using Jupyter or other
locally hosted visualization tools) add the `-L` flag:

```bash
ssh -L 8888:127.0.0.1:8888 <odin_id>@login1.coeus.rc.pdx.edu
```

The port numbers (8888) can be replaced to anything as long as
the port is available and not reserved for specific uses.

### Connecting from outside the PSU network

Instructions for connecting from outside the network exist at these
two locations:
- [VPN method (preferred)](https://sites.google.com/pdx.edu/research-computing/faqs/remote-access/remote-vpn)
- [Tunneling method](https://sites.google.com/pdx.edu/research-computing/faqs/remote-access/remote-ssh)

[More information about connecting in general is here.](https://sites.google.com/pdx.edu/research-computing/faqs/system-access?authuser=0)

## Navigation and File Management

Once authenticated and logged in to `coeus` you will be placed in
your home directory, `/home/<odin>`. The 'print working directory'
tool `pwd`. The absolute basic commands you will need to know:

- `ls` lists the files in the current directory
- `cd <name>` change directory
- `cp <source> <dest>` copy a file
- `mv <source <dest>` move a file or directory
- `mkdir <name>` creates a new empty directory
- `rm <file>` deletes a file, careful you cannot undo this without help from OIT
and even then there is no guarantees
- `cat <file>` print contents of a file

Each of these tools has additional options or flags that modify the
behavior. For example:

- `ls -l` (long) displays more information about each
file like the permissions and size
- `ls -lh` (human) but the file sizes aren't really human readable
so this helps with that
- `ls -a` (all) shows even hidden files (files starting with `.` are
hidden)

To learn about any command use the `man` (manual) command. 
For example, `man man` will teach you about `man` and `man ls` will
teach you about `ls`. Search these `man` pages with the `/` key.
Learning to utilize the manual is the best way to become efficient
at using Linux systems.

## Moving files with `SFTP`

Moving files back and forth between the RC filesystems and your
personal device requires another tool. `sftp` is very similar
to `ssh` that provides an encrypted connection for file transfers.

The easiest way to use `sftp` is in interactive mode.

```bash
sftp <odin>@login2.coeus.rc.pdx.edu
```

This will give a prompt similar to when you `ssh` but has different
functionality. You can navigate the filesystem the same way, but now
you have two new essential commands:

- `get <file>` downloads the file to your local device to the directory
that you ran the `sftp` command from
- `put <file>` uploads a file to `coeus` into the directory that your
`sftp` prompt is located in

There are many interactive `sftp` clients which may be easier to use,
I suggest the open source client FileZilla. Other popular clients
include WinSCP and Cyberduck. Popular code editors like VS Code and
IntelliJ have plugins that provide file transfer functionality as well.
