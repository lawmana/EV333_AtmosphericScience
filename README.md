# EV333_AtmosphericDynamics
Repository for EV333 Atmospheric Dynamics at Colorado College. 

# Getting Started with Python

***We will go over all of the instructions below during the first week of class.***

## 1. [Install Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)
Anaconda is a distribution of the Python programming language that simplifies package management. It is very popular for data science. Miniconda is a small version of Anaconda that includes the conda package manager, Python, and a few packages. Conda will help you easily install Python packages. 

You will install miniconda and Python on your personal computer for this class. The installation instructions will be different depending on whether you have a Mac or Windows computer. The following steps 2-6 will be the same for both operating systems.

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
**Option A: Try this option first**

1. Go to the Miniconda installation webpage: https://docs.conda.io/projects/miniconda/en/latest/
2. Click on the option for the Windows Platform `Miniconda3 Windows 64-bit`. The option is outlined with a red rectange in the image below. This will start the download.
  
![MinicondaWindows](https://github.com/lawmana/EV333_AtmosphericDynamics/assets/29742094/5d4d89a0-2208-4127-982c-5a9494f01523)

4. Once downloaded, double click to open. Then follow the prompts to complete the installation.
6. First you will need to agree to the license agreement.
7. When prompted to **Select Installation Type** select the **Just Me (recommended)** option.
8. When prompted to **Choose Install Location**, use the default location that is provided. This will typically look something like: `C:\Users\YourUserName\miniconda3`
9. For the **Advanced Installation Options**, check the box that says to **Add Miniconda3 to my PATH environment variable**.
10. Click **Install**. The installation may take some time.
11. Once the installation is complete click **Next** and then **Finish.**
12. To verify that conda is installed correctly, open a command prompt and type `conda.` If this command displays output this indicates that your conda installation is complete.
13. To check which version of Python you have installed: 
```
python --version
```
You should have Python 3.11.

**Option B: Only try this if Option A does not work**
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
conda create --name Atmo_EV333
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
We will use [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/latest/) for all lab assignments that involve coding. Jupyter Notebook is an open-source application that allows users to create interactive documents that can contain live code, equations, visualizations, and narrative text. Notebooks will contain blocks of text and executable Python code. Notebooks have the file extension `.ipynb`.

To install Jupyter Notebook:

1. Ensure that you are in your Atmo_EV333 environment (see Step 3 above)
2. In the terminal: 
```
pip install notebook
```

## 5. Install additional Python packages
We will work with the following Python packages. Please install all of the packages one at a time. If conda asks you to proceed, type `y`:

```
proceed ([y]/n)?
```

- [Matplotlib](https://matplotlib.org/stable/): 
```
conda install -c conda-forge matplotlib
```
- [SciPy](https://scipy.org/install/):
```
conda install scipy
```
- [Xarray](https://docs.xarray.dev/en/latest/getting-started-guide/installing.html):
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

Check that all of the packages were successfully installed:
```
conda list
```
Xarray should install Numeric Python ([NumPy](https://numpy.org/install/)) by default, but check that numpy is there.

## 6. Create a directory on your computer for your EV333 course work.

1. Create a new folder (directory) for EV333. For example a directory called `EV333_AtmosphericDynamics` in your Documents folder or wherever you store your course materials.

2. Navigate to this directory using the command line. You will specify the full path to the directory. The command may look something like this (on a Mac), but the path will be for your personal computer:
```
cd /Users/alawman/Documents/Python/EV333_AtmosphericDynamics
```
`cd` means change directory. The command `pwd` will print your current working directory (in Mac/Linux terminals). 

## 7. Launch Jupyter Notebook and test your installation
While in the `EV333_AtmosphericDynamics` directory, launch Jupyter Notebook by entering following in the terminal:
```
jupyter notebook
```
This will launch a new tab in your browser. 

1. Open the Notebook: `EV333_Test_Required_Packages.ipynb`
2. Run the first cell. This will check if NumPy, Xarray, Matplotlib, SciPy, and Cartopy are successfully installed. A `Y` for everything means you're ready to go!
