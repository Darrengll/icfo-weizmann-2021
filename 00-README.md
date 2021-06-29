# Introduction

This folder contains a number of Jupyter notebooks that include tools and exercises for the [ICFO-Weizmann 2021 Summer School Frontiers on the Frontiers of Light](https://frontiers.icfo.eu/home-2021/). They were used in the tutorial section led by [Juan José García Ripoll](https://quinfog.hbar.es/members/juan-jose-garcia-ripoll) on the simulation of superconducting circuits.

The instructions are very simple:

1. Read this file, the [README](file:00-README.md) file, for instructions on how to set-up a minimalistic Python environment and run the exercises.

2. Choose one or more of the exercises, depending on your interests and level.

3. For each notebook, first make sure you can run the complete examples.

4. Then try to fulfill the following exercises and, optionally, address one of the challenges at the end of the notebook or create your own.

5. Feel free to ask questions at the Discord channel of the summer school or, once it is finished, you can also reach me out by [email](https://quinfog.hbar.es/members/juan-jose-garcia-ripoll) or by [Twitter](https://twitter.com/jjgarciaripoll).

# Setting up Miniconda

In order to run the exercises you will need a working and up-to-date Python 3 environment. My personal recommendation is to go with the simple, yet very functional distribution called [Miniconda](https://docs.conda.io/en/latest/miniconda.html). This distribution only contains a minimal Python environment that you need to complete by downloading required packages. I find it is the best option because it is free of clutter and fits in any computer.

The steps to set up this distribution on Windows are

1. Download the Python 3.9 [Miniconda](https://docs.conda.io/en/latest/miniconda.html) distribution.

2. Execute the installer and choose the option that installs is only for this user. This will create a folder called `~/miniconda3` in your /home/ directory, as well as icons for a Miniconda terminal.

3. Open the Anaconda terminal and enter the following commands, one after another (wait for the previous one to complete)
```
conda update --all
conda create -n school
conda activate school
conda install numpy scipy jupyterlab matplotlib
```

The first step updates the Miniconda distribution. The second step creates a Python environment only for this summer school. The third step activates the environment; you have to type this every time you open a new terminal, to select the configuration that we will use. The fourth step configures the `school` Python environment with a small set of libraries that we will need in the exercises.

Once you have installed Python, you can open the Jupyter notebooks for the exercises using the terminal. Launch the Anaconda terminal, activate the Python environment
```
conda activate school
```
and change directory to the place where you downloaded or unpacked the exercises
```
cd c:\Users\juanjo\ICFO-Weizmann-2021
```
At that point you should be able to see this file and the notebooks:
```
dir "00-README.md"
```
You can then launch the Jupyter Lab programming environment as
```
jupyter lab
```
A browser will open, pointing typically to the URL `localhost:8888/lab` or a similar address. On the left of the browser you will see a folder icon that allows you to see the list of files, open this README file or open the notebooks.

# Learning about advanced Python functions

In this school we are going to use routines that perform advanced operations on matrices and vectors, which is the way we represent Hamiltonians and states in a computer. In order to understand what we will be doing, I recommend that you read the following material.

- The description of the routine `eigsh` in the [Scipy reference manual](https://docs.scipy.org/doc/scipy/reference/generated/scipy.sparse.linalg.eigs.html).

- The description of the routine `expm_multiply` in [the Scipy manual](https://docs.scipy.org/doc/scipy/reference/generated/scipy.sparse.linalg.expm_multiply.html)

- The examples on sparse matrices in the [Scipy reference](https://docs.scipy.org/doc/scipy/reference/sparse.html) or [related tutorials](https://medium.com/swlh/an-in-depth-introduction-to-sparse-matrix-a5972d7e8c86). We will typically be using `csr_matrix` and `lil_matrix`, because the former supports efficient matrix-vector multiplication, while the latter allows for arbitrary constructs. However, you should also learn about the `diags` function, or how to modify and extract parts of matrices.

Read also carefully some of the examples in the exercises, which will also use similar functionalities.