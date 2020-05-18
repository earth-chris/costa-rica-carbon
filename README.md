# costa-rica-carbon
Forest carbon mapping utilities for Stanford / NatCap / NASA / GEO-BON biodiversity and ecosystem services quantification in Costa Rica.

## Setup

This workflow is designed to install and run via `conda`. You can find `conda` install instructions [here][home-conda]. 

```
# download the repository
git clone https://github.com/earth-chris/costa-rica-carbon.git
cd costa-rica-carbon

# install the conda package
conda env update
conda activate carbono
```

The one non-traditional dependency here is the `ccb` package, a python wrapper for species distribution modeling and machnie learning. You can read about the `ccb` package [on GitHub][home-ccb]. Download and install this package within the `costa-rica-carbon` directory.

```
# download and install the ccb package
git clone https://github.com/stanford-ccb/ccb.git
cd ccb
pip install -r requirements.txt
python setup.py install

# the following is optional to use the ccb default ipython config
conda env config vars set IPYTHONDIR=$PWD/ipython
```

## Notebooks

Once you're in the `carbono` conda environment, run `jupyter notebook` to access and run the notebooks. These are organized by the order in which they should be run.

* `01-data-processing.ipynb` is where the brute-force geospatial data processing occurs, and precedes all modeling.
* `02-modeling.ipynb` is where the tree height and carbon modeling occurs 

## Datasets

All data used here are stored in the team's Google Drive directory under `NASA - Costa Rica/Costa Rica Data/Chris data`. Download the following files to run these notebooks:

```
lvis-lidar-pts-32616.*
fcover.tif
radar.tif
tree-cover.tif
```

Download and store these files in the `costa-rica-carbon/data/` directory. Additional data processing is handled in the `01-data-processing.ipynb` notebook, which performs no-data handling and other data manipulation tasks.

A note of warning -- these datasets are fairly large, and a series of large temporary files are created along the way. Make sure you have a few gigabytes of storage available for processing.