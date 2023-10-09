# EV333_AtmosphericDynamics
Repository for EV333 Atmospheric Dynamics at Colorado College

# Getting Started

# [Instructions for Installing Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)
## macOS (M1)
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

4. To check which version of Python you have: (should be Python 3.11.6)
```
python --version
```

## Creating a new Python environment
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

## Activating your Python environment
```
conda activate Atmo_EV333
```
To view your list of environments:
```
conda env list
```
An `*` indicates the active environment

## Installing Python libraries and packages
```
conda list
```

## Launch Jupyter 
