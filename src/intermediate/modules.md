# Modules

Many users of the cluster have different software
requirements that are often conflicting. The
`module` system provides an interface for setting
environment variables to provide access to custom software.

Some of the available software is listed on the
OIT RC [software page](https://sites.google.com/pdx.edu/research-computing/software).

Common module commands:
- `module avail` lists the available modules
- `module list` list the currently loaded modules
- `module load <module_name>`
- `module remove <module_name>`
- `module purge` removes all loaded modules

Generally these have tab completion. Sometimes the `PATH` variable
isn't correctly restored when loading and unloading modules, the
best fix is to exit out of the session and `ssh` back in.
