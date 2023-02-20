# Slurm

[Slurm](https://slurm.schedmd.com/documentation.html)
is the workload scheduler that allocates computing resources 
when requested. Users can submit job requests to Slurm from
the login node which will be placed in the work queue.

[OIT-RC's Slurm page](https://sites.google.com/pdx.edu/research-computing/getting-started/slurm-scheduler)
contains a lot of good information about the topic.

The computing resources are divided into *partitions*. These
partitions have different quantities and types of nodes as
well as different restrictions on how long a job can run for.
Generally when submitting a job you will select a number of nodes,
how many *process sockets* to allocate on each node, and which
partition. Examples of different approaches to using Slurm with
NGSolve are detailed in the NGSolve chapters of this guide.

## Some usefull Slurm commands
- `squeue -u <odin>` will show you your queued and running jobs
- `sinfo` gives info about the cluster like partition types and node status
- `scancel <job_id from squeue>` will terminate a running batch job or interactive session
- `salloc` requests a compute node for an interactive (shell) session
