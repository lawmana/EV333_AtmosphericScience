# EV333_AtmosphericDynamics
Repository for EV333 Atmospheric Dynamics at Colorado College

# Getting Started

## 1. [Install Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)
### macOS (M1 chip)
1. Run the following four commands in a terminal:
```
mkdir -p ~/miniconda3
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh -o ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -rf ~/miniconda3/miniconda.sh
```
2. Initialize the zsh shell:
```
~/miniconda3/bin/conda init zsh
```
3. Close and relaunch the terminal

5. To check which version of Python you have installed: 
```
python --version
```
You should have Python 3.11.

### Windows
1. Run the following four commands in a terminal:
```
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe -o miniconda.exe
start /wait "" miniconda.exe /S
del miniconda.exe
```
2. Initialize the zsh shell:
```
~/miniconda3/bin/conda init zsh
```
3. Close and relaunch the terminal

5. To check which version of Python you have installed: 
```
python --version
```
You should have Python 3.11.

## 2. Create a new Python environment
[Additional documentation for creating an environment with commands](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands)
1. Open the terminal.
2. To create an environment called Atmo_EV333 for this course:
```
conda create --name Atmo_EV33
```
3. When conda asks you to proceed, type `y`:
```
proceed ([y]/n)?
```
This creates the Atmo_EV333 environment. 

## 3. Activate your Python environment
```
conda activate Atmo_EV333
```
To view your list of environments:
```
conda env list
```
Your system may look something similar to this. An `*` indicates the active environment:
```
# conda environments:
#
base                     /Users/alawman/miniconda3
Atmo_EV333            *  /Users/alawman/miniconda3/envs/Atmo_EV333
```


## 4. Install Jupyter Notebook
In this class we will use [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/latest/) for running code. 
1. Ensure that you are in your Atmo_EV333 environment (see Step 3 above)
2. In the terminal: 
```
pip install notebook
```

## 5. Install additional Python packages
We will work with the following Python libraries. Install one at a time.

- [Matplotlib](https://matplotlib.org/stable/): 
```
conda install -c conda-forge matplotlib
```
- SciPy:
```
conda install scipy
```
- [Xarray]():
```
conda install -c conda-forge xarray dask netCDF4 bottleneck
```
- [cartopy](https://scitools.org.uk/cartopy/docs/latest/index.html): geospatial data processeing to produce maps and other geospatial data analyses
```
pip install cartopy
```
- [cmocean](https://matplotlib.org/cmocean/#installation): color palettes for maps
```
conda install -c conda-forge cmocean
```

Check that all of these libraries were installed successfully:
```
conda list
```
Xarray should install Numeric Python ([NumPy](https://numpy.org/install/)) by default, but check that numpy is there.

## 6. Create a place to store your EV333 course work.

1. Create a new folder (directory) for EV333. For example a directory called `EV333_AtmosphericDynamics` in your Documents folder or wherever you store your coursework.

2. Navigate to this directory using the command line. You will specify the full path to the directory. It may look something like this, but the path will be for your personal computer.
```
cd /Users/alawman/Documents/Python/EV333_AtmosphericDynamics
```
`cd` means change directory. The command `pwd` will print your current working directory. 

## 7. Launch Jupyter Notebook and test your installation
Launch Jupyter Notebook by typing the following command:
```
jupyter notebook
```
This will launch a new tab in your browser. 

1. Open the Notebook: `EV333_Test_Required_Libs.ipynb`
2. Run the first cell. This will check if NumPy, Xarray, Matplotlib, SciPy, and Cartopy are successfully installed. A `Y` for everything means you're ready to go!
