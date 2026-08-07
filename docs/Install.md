# Installation

## conda/pip

PyGlider depends on `dask` and `netcdf4`, both of which can be tricky to install using `pip`,
hence we recommend these be installed with [`conda`](https://www.anaconda.com/). To install
PyGlider, create an environment, and do

```
conda create -n gliderwork
conda activate gliderwork
conda install -c conda-forge pyglider
```

### pixi

If you prefer [`pixi`](https://pixi.io/) to conda, you can install PyGlider with

```
pixi init
pixi add pyglider
```

### Slocum glider users: dbdreader

If you work with Slocum glider data, PyGlider uses [`dbdreader`](https://dbdreader.readthedocs.io/en/latest/) to read the raw binary files. `dbdreader` is a required dependency when installing from PyPI with `pip`, so it will already be present in that case. However, the `pyglider` conda-forge package does not currently pull in `dbdreader`, so if you installed with `conda install -c conda-forge pyglider` or `pixi add pyglider`, install it separately:

```
conda install dbdreader
```

or with pixi:

```
pixi add dbdreader
```

## Editable installation

If you want to be able to edit the files in `pyglider/pyglider` then install
the dependencies as above. Fork of PyGlider on github, and then clone it locally:

```
git clone https://github.com/yourname/pyglider.git
```

Navigate to the new `pyglider` directory and then do `pip install -e .`.
That will re-install pyglider with links to the local directory, so you
can edit the library files. If you do so, consider making a pull-request
with your changes!

### pixi editable installation:

Edit your `pixi.toml` file to include the following:

```
pypi-dependencies:
    pyglider = { path = ".", editable = true }
```

Note that the repo has a `pyproject.toml` with optional pixi tooling that should work just with just

```
pixi install
```

if you execute from the repo root.