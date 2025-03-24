# EV333_AtmosphericScience
Repository for EV333 Atmospheric Science at Colorado College. 

# Getting Started with Python

***We will go over the instructions below during the first week of class.***

## 1. [Install Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)
Anaconda is a distribution of the Python programming language that simplifies package management. It is very popular for data science. Miniconda is a small version of Anaconda that includes the conda package manager, Python, and a few packages. Conda will help you easily install and manage Python packages and environments. 

You will install miniconda and Python on your personal computer for this class. You will need to download the installer for your platform (macOS or Windows). **Important Note: If you already have Anaconda or miniconda installed on your computer (eg., from another class), skip to the next step.**

***<ins>If you have a Mac:<ins>** You will need to check which processor you have (Intel or Apple M1). To do this, click on the Apple icon in the upper left corner of your screen and go to **About this Mac***.

1. Go to the Miniconda installation webpage: https://www.anaconda.com/docs/getting-started/miniconda/install
2. Click the Basic install instructions that are approproate for your operating system (Windows or MacOS/Linux).
3. Work through the install instructions provided (you will need to enter your email address to download miniconda).
4. Choose the **64-Bit Graphical Installer** option that is appropriate for your operating system.
5. Follow the prompts to complete the installation. You will need to agree to the license agreement and select the destination for the installation. For the desintation, choose the default path that populates automatically.
6. Click **Install**. The installation may take some time.
7. Once the installation is complete click **Next** and then **Finish.**
8. To verify that conda is installed correctly, open a new terminal and type `conda`. If this command displays output this indicates that your conda installation is complete.

## 2. Create a directory on your computer for your EV333 course work.

1. Create a new folder (directory) for EV333. For example a directory called `EV333_AtmosphericScience` in your Documents folder or wherever you store your course materials.

2. Navigate to this directory from the command line. You will specify the full path to the directory. The command may look something like this (on a Mac), but the path will be for your personal computer:
```
cd /Users/alawman/Documents/Python/EV333_AtmosphericScience
```
`cd` means change directory. The command `pwd` will print your current working directory. The command `ls` (MacOS/Linux) or `dir` (Windows) will list all the files and directories in the working directory.

3. Download the text file `requirements.txt` from this GitHub repository and transfer it to your `EV333_AtmosphericScience` directory.

## 3. Add conda-forge 
1. Open the terminal (Mac) or command prompt (Windows).
2. Copy and paste the following line and then hit return/enter:
```
conda config --add channels conda-forge
```

## 4. Create a new Python environment
[Additional documentation for creating an environment with commands](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands)
1. To create an environment called **Atmo_EV333** for this course with a specific version of Python (here Python 3.11) and the packages you will need for this course, copy and paste the following line:
```
conda create --name Atmo_EV333 --file requirements.txt
```
This creates the Atmo_EV333 environment. 

The following Python packages were installed: [NumPy](https://numpy.org/doc/stable/index.html), [Matplotlib](https://matplotlib.org), [Cartopy](https://scitools.org.uk/cartopy/docs/latest/), [SciPy](https://scipy.org), [cmocean](https://www.google.com/search?client=safari&rls=en&q=cmocean&ie=UTF-8&oe=UTF-8).


## 5. Activate your Python environment
In the terminal (Mac) or Command Prompt (Windows):
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

## 6. Install additional Python packages

Install NetCDF4 by copying and pasting the following line in the terminal or Command Prompt:
```
pip install netCDF4==1.6.2
```

Check that all of the packages were successfully installed:

```
conda list
```

## 7. Launch Jupyter Notebook and test your installation
We will use [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/latest/) for all lab assignments that involve coding. Jupyter Notebook is an open-source application that allows users to create interactive documents that can contain live code, equations, visualizations, and narrative text. Notebooks will contain blocks of text and executable Python code. Notebooks have the file extension `.ipynb`.

1. Download the Notebook `EV333_Test_Required_Packages.ipynb` from this GitHub repository and transfer it to your `EV333_AtmosphericScience` directory.

2. Navigate to your `EV333_AtmosphericScience` directory from the command line. Then launch Jupyter Notebook by entering following in the terminal:
```
jupyter notebook
```
This will launch a new tab in your browser. 

3. Open the Notebook: `EV333_Test_Required_Packages.ipynb`
4. Run the first cell by clicking the play button. This will check if NumPy, Xarray, Matplotlib, Cartopy SciPy, cmocean, and the NetCDF4 packages are successfully installed. If you receive an `N` for any package, double check that you installed the package in your Atmo_EV333 environment. A `Y` for everything means you're ready to go!

## 8. Create a reference guide for launching Jupyter Notebook

1. Write down the steps and commands you need to launch Jupyter Notebook (additional instructions will be provided in class).
2. Shut down Jupyter Notebook
3. Quit your terminal (Mac) or command prompt (Windows)
4. Download the `EV333_Intro.ipynb` notebook into you `EV333_AtmosphericScience` directory.
5. Launch the EV333_Intro using Jupyter Notebook using only your reference guide. Revise your instructions if needed.

## 9. Begin practicting Python!
Begin working through the EV333_Intro instructions to start gaining familiarity with Python.
