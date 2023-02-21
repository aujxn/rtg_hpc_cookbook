# Python Virtual Environments

Python's tool for managing dependencies and packages is `pip`.
The standard Python package index is called `PyPI`. Packages
indexed in `PyPI` can be installed by doing
`pip install <package_name>`. This will use the version of
python available in your `PATH` and probably install the
package into a hidden folder in your home directory.

Often times you want to be able to use specific versions of
Python and different versions of library dependencies for
various projects. [The standard Python virtualization tool](https://docs.python.org/3/library/venv.html)
is called `venv`.

Alternatives to `venv` such as `conda` and `spack` exist but
are used for creating virtual environments that manage more
than just Python dependencies. These tools are more complex
but offer more functionality.

Start by loading a Python module,
```bash
module load Python/<version>
```

Check that `python3 --version`
and `which python3` give sensible outputs.

Create a new environment with
```bash
python3 -m venv <dir_name>
```
where `<dir_name>` is the name of the directory to place the
environment files. You can also specify a full path here.

Source the environment with
```bash
source <dir_name>/bin/activate
```

You will see the environment name next to your shell prompt
indicating that it is active. Running a `which python3` should
provide the binary located in the `venv` directory created.

You will need to source this environment each session or put
the source command in your `.bashrc`. You will also want to
source the environment after loading modules in any `sbatch`
scripts.

Once active, dependencies can be installed to the environment
with `pip`:
```bash
pip install <dep_name>
```
will install the package to
`<dir_name>/lib64/python<version>/site-packages` which is
automatically added to the `PYTHONPATH` variable when the
Python binary associated with the environment is invoked.
