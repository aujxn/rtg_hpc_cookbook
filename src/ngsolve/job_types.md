# Submitting Jobs

## Interactive jobs and development
Sometimes you will want to work in an interactive session for
testing and debugging purposes. For this I would suggest working
in a single node:
```bash
salloc --nodes 1 --ntasks 20
```
This should output something like:
```
salloc: Granted job allocation 5681935
salloc: Waiting for resource configuration
salloc: Nodes compute033 are ready for job
```
with a different job ID and node. Here we got node `033` so `ssh`
into this machine and load the module like we did during setup:
```bash
ssh compute033
module load ngsolve/parallel/6.2.2301
```
If you didn't put automatic loading of your virtual environment in
your `.bashrc` then source that now.

Then you should be all ready to go! Try running an example with:
```bash
mpirun python3 $NGSOLVE_SRC/py_tutorials/mpi/mpi_cmagnet.py
```

## Batch jobs
Although more than a single node can be used in an interactive session
the suggested method for submitting multi-node jobs is using `sbatch`
with a configuration script.

In this case, working on the login node is fine. Create a file called
`submit.sh` and copy the contents:
```bash
#!/bin/bash
#SBATCH --job-name example_job
#SBATCH --nodes 6
#SBATCH --ntasks-per-node 10        # less than 2 cores per proc is unstable
#SBATCH --output=out.log
#SBATCH --output out_%j.txt
#SBATCH --error out_%j.err
#SBATCH --partition medium

pwd; hostname;
echo "Starting at wall clock time:"
date
echo "Running CMT on $SLURM_CPUS_ON_NODE CPU cores"

module load ngsolve/parallel/6.2.2301
source $HOME/venv/bin/activate     # Change this to your venv path

mpirun python3 $NGSOLVE_SRC/py_tutorials/mpi/mpi_cmagnet.py

echo "Ending at wall clock time:"
date
```
This is a good starting place to work from. To submit the job:
```bash
sbatch submit.sh
```


