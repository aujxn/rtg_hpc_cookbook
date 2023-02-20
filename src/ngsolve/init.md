# Initial Setup

These steps should only be done once when setting up your development
environment.

## Get source code for examples and demos
To run the example codes (found in the NGsolve source) clone the repo:
```bash
git clone https://github.com/NGSolve/ngsolve
```

- To simplify scripts in the future save this path into an environment
variable and add that definition to the `.bashrc` configuration file:
```bash
cd ngsolve
export NGSOLVE_SRC=`pwd`
echo $NGSOLVE_SRC >> $HOME/.bashrc
```
Note: those are backticks (not apostrophies) to run the `pwd` command.

## Setting up a development environment
- Load the NGSolve module:
```bash
module load ngsolve/parallel/6.2.2301
```
This module depends on `gcc-12.1`, `intel`, `openmpi-4.1.4` and
`python3` modules but loads them all automatically.

- Create a python environment and install dependencies:
```bash
python3 -m venv $HOME/venv
source $HOME/venv/bin/activate
pip install --upgrade pip
pip install mpi4py numpy scipy matplotlib plotly
```
Notes:
- Add whatever other python dependencies you need
- I like to use a single environment for everything in my home
directory but if you want multiple projects with different
dependency requirements this is a less than ideal strategy
- To automatically source this environment on login add the
`source` command to your `.bashrc` by:
`echo "source $HOME/venv/bin/activate" >> $HOME/.bashrc`


