# Editors

There are many choices when deciding how to edit your source
files.

## Terminal based

Terminal editors such as `Vim`, `Vi`, `Emacs`, and `Nano`
allow you to edit files directly from the shell on the cluster.
These editors can be extremely powerful and integrate well
with existing Linux tools but generally require more set up
and practice to become efficient with.

For tips on configuring `Vim` there is a chapter in the advanced
section with some suggestions.

## Integrated Development Environments (IDEs)

IDEs offer a more complete and configured suite for development.
IDEs can be extremely powerful by providing a framework for tasks
such as:

- managing build tools
- editing
- syntactic language support
- language servers
- virtual environments

and many others.

IDEs come preconfigured and usually have systems for extensions
and configuration through a graphical interface. Some popular
IDEs include:

- vscode
- intellij
- spyder

These IDEs can all be set up to connect remotely to the RC resources
and can even be configured to integrate with Slurm.

## Notebooks (browser based)

IDEs and terminal editors often have the capability to run code
notebooks such as Jupyter (`.ipynb` files) but these notebooks
are generally edited and run within a web browser. Using a notebook
on the cluster is common way to get nice graphical interfaces when
working on remote servers.

Notebooks provide a block abstraction with generally 2 formats:
- `code` blocks which can be executed individually.
This is convenient for testing and debugging.
- `markdown` blocks which allow for description with standard
markdown syntax. The style of pairing each code block with a
description block is often called *literate programming* coined
by Donald Knuth and heavily utilized in fields of data science.
These markdown blocks also support a subset of the *LaTeX*
language which is nice for us mathematicians.

Notebooks can be setup to automatically submit parallel jobs through
Slurm but I have personally had trouble getting this feature set up
and functioning.
