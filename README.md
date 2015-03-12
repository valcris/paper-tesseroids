# Tesseroidds: forward modeling of gravitational fields in spherical coordinates

by [Leonardo Uieda](http://www.leouieda.com/) et al.

This is a draft of a paper about the open-source software package
[Tesseroids](http://tesseroids.leouieda.com).
It also describes an optimal method for modeling gravitational
fields due to spherical prism mass elements (tesseroids).

## Reproducing the results

The [IPython notebooks](http://ipython.org/notebook.html) located in the
`notebooks` directory of this repository
generate all data, results, and figures in this paper.
They use Tesseroids, [Fatiando a Terra](http://fatiando.org),
and libraries from the [Scipy ecosystem](http://scipy.org/)
to perform the calculations and generate figures.
Data generated by the notebooks is stored in the `data` directory.

You can view a static version of the notebooks from the
[nbviewer](http://nbviewer.ipython.org/) web service:

* [Figures for the Methodology section](http://nbviewer.ipython.org/github/pinga-lab/paper-tesseroids/blob/master/notebooks/methods_figures.ipynb)
* [Results and preliminary figures for comparison with a spherical shell](http://nbviewer.ipython.org/github/pinga-lab/paper-tesseroids/blob/master/notebooks/tesseroid_vs_spherical_shell.ipynb)
* [Final version of results figures for the article](http://nbviewer.ipython.org/github/pinga-lab/paper-tesseroids/blob/master/notebooks/results-figures.ipynb)

### Getting the files

To actually run the code in the notebooks,
you'll need to have the files on your machine.
You can download a 
[zip archive of this repository](https://github.com/pinga-lab/paper-tesseroids/archive/master.zip)
to get everything.

### Installing the software

First, you'll need to download the Tesseroids v1.2 software.
You can get the source code and compiled binaries from:

* The official site: hhtp://tesseroids.leouieda.com
* Zenodo: **INCLUDE DOI FOR v1.2**

Unpack the executables (or compile the code) and place them
somewhere included in your PATH environment variable
(so that your terminal or `cmd.exe` can find them).

Next, you'll need to install Python and the required libraries
to execute the IPython notebooks.
The easiest way to get Python and all libraries installed 
is through the
[Anaconda Python distribution](http://continuum.io/downloads).
Be sure to select the **Python 2.7** version of Anaconda.
After you've installed Anaconda, 
install the libraries by running the following command
in your terminal:

    conda install numpy scipy ipython matplotlib mayavi imaging pandas basemap pip

After Anaconda, you'll need to install the geophysics library
[Fatiando a Terra](http://www.fatiando.org).
You can do this by running the following command
in your terminal:
 
    pip install fatiando==0.3

**Note to Windows users**: See the 
[documentation of Fatiando a Terra](http://fatiando.github.io/v0.3/install.html) 
for extra software you'll need.

### Running the IPython notebooks

Once the software is installed, you must start an IPython notebook server to
run the code in the notebooks.
Do this by typing in a terminal (or `cmd.exe` in Windows):

    ipython notebook

This should open an Internet browser tab with a page to navigate your computers
folders.
Go to where you saved the `notebooks` folder on your computer and click on
the notebook file you want to run.
You can execute the code cells by clicking on one and typing `Shift+Enter`.
Be sure to execute the code cells in descending order to get the correct
results.
Some cells may take a long time to run, particularly those that calculate the
tesseroid fields.

## Compiling the manuscript

The main body of the text is in `manuscript.tex`.

The `Makefile` contains rules to compile the manuscript. Use `make` without any
arguments to generate the PDF:

    make

You can run the [write-good](https://github.com/btford/write-good)
English language checker on the manuscript
(this is not a spell checker):

    make check

Run write-good on the IPython notebooks:

    make check-notebooks

Spell check the manuscript using `aspell`:

    make spell

Count words on the manuscript
(uses [detex](http://www.ctan.org/tex-archive/support/detex)
to strip the Latex commands from the file):

    make words

