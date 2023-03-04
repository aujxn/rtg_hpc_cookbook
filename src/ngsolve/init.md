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
`python3.10` modules but loads them all automatically.

In this module:
- The version of NGSolve is `6.2.2301`
- Built with CMake command: 
```bash
cmake /home/ajn6/source_repos/ngsolve/ngsolve_src \
-DCMAKE_INSTALL_PREFIX=/vol/apps/ngsolve/parallel/ngs-6.2.2301_openmpi-4.1.4_gcc-12.1.0 \
-DCMAKE_C_FLAGS= -ffunction-sections -fdata-sections -fPIC -m64 \
-DCMAKE_C_COMPILER=/vol/apps/gcc/gcc-12.1.0/bin/gcc \
-DCMAKE_CXX_FLAGS= -ffunction-sections -fdata-sections -fPIC -m64 \
-DCMAKE_CXX_COMPILER=/vol/apps/gcc/gcc-12.1.0/bin/g++ \
-DCMAKE_ASM_FLAGS= -ffunction-sections -fdata-sections -fPIC -m64 \
-DCMAKE_ASM_COMPILER=/vol/apps/gcc/gcc-12.1.0/bin/gcc \
-DCMAKE_BUILD_TYPE=opt-level=3 \
-DUSE_OCC=OFF \
-DPYTHON_EXECUTABLE:FILEPATH=/vol/apps/python/gcc/3.10.10/bin/python3 \
-DPYTHON_LIBRARY=\'/vol/apps/python/gcc/3.10.10/lib/libpython3.10.a\' \
-DPYTHON_INCLUDE_DIR=\'/vol/apps/python/gcc/3.10.10/include/python3.10\' \
-DUSE_GUI=OFF \
-DUSE_MKL=OFF \
-DUSE_HYPRE=ON \
-DSUPERBUILD=ON \
-DMKL_SDL=OFF \
-DUSE_MPI=ON
```

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


