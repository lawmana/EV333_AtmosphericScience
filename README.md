# EV333_AtmosphericDynamics
Repository for EV333 Atmospheric Dynamics at Colorado College. 

# Getting Started with Python

***We will go over all of the instructions below during the first week of class.***

## 1. [Install Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)
Anaconda is a distribution of the Python programming language that simplifies package management. It is very popular for data science. Miniconda is a small version of Anaconda that includes the conda package manager, Python, and a few packages. Conda will help you easily install and manage Python packages and environments. 

You will install miniconda and Python on your personal computer for this class. You will need to download the installer for your platform (macOS or Windows). The following steps 2-6 will be the same for both operating systems. 

***<ins>Important note if you have a Mac:<ins>** You will need to check which processor you have (Intel or Apple M1). To do this, click on the Apple icon in the upper left corner of your screen and go to **About this Mac***

1. Go to the Miniconda installation webpage: https://docs.conda.io/projects/miniconda/en/latest/
2. Click the installer that is approproate for your platform (see image below): Windows (red), macOS Intel (orange), macOS M1 (purple). This will start the download.
<img width="1071" alt="MinicondaInstaller" src="https://github.com/lawmana/EV333_AtmosphericDynamics/assets/29742094/88aa0776-204e-4883-849c-ac5f51f046c8">

4. Once downloaded, double click to open. Then follow the prompts to complete the installation. You will need to agree to the license agreement and select the destination for the installation. For the desintation, choose the default path that populates automatically.

***For Windows:***

4a. When prompted to **Select Installation Type** select the **Just Me (recommended)** option.

4b. When prompted to **Choose Install Location**, use the default location that is provided.

4c. For the **Advanced Installation Options**, check the boxes to (see image below):
![AnacondaWindows](https://github.com/lawmana/EV333_AtmosphericDynamics/assets/29742094/511228e7-4fed-4e1e-9271-9aeafc2a5556)

5. Click **Install**. The installation may take some time.
6. Once the installation is complete click **Next** and then **Finish.**
7. To verify that conda is installed correctly, open a command prompt and type `conda.` If this command displays output this indicates that your conda installation is complete.

## 2. Create a new Python environment
[Additional documentation for creating an environment with commands](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands)
1. Open the terminal (Mac) or command prompt (Windows).
2. To create an environment called **Atmo_EV333** for this course with a specific version of Python (here Python 3.11) and some of the Python packages you will need for this course, copy and paste the following line:
```
conda create --name Atmo_EV333 python=3.11 numpy xarray matplotlib cartopy scipy
```
3. When conda asks you to proceed, type `y`:
```
proceed ([y]/n)?
```
This creates the Atmo_EV333 environment. The following Python packages are installed: [NumPy](https://numpy.org/doc/stable/index.html), [Matplotlib](https://matplotlib.org), [Cartopy](https://scitools.org.uk/cartopy/docs/latest/), and [SciPy](https://scipy.org). 

## 3. Activate your Python environment
In the terminal (Mac) or Command Prompt (Windows)
```
conda activate Atmo_EV333
```

To check which version of Python you have for this environment:

```
python --version
```
You should have Python 3.11.


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
2. In the terminal (Mac) or Command Prompt (Windows): 
```
conda install -c conda-forge notebook
```

## 5. Install additional Python packages

- [cmocean](https://matplotlib.org/cmocean/#installation): color palettes for maps
```
conda install -c conda-forge cmocean
```
When asked if you want to proceed, type `y`:
```
proceed ([y]/n)?
```

Check that all of the packages were successfully installed:

```
conda list
```

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
