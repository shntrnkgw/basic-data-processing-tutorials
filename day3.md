# Basic data processing tutorials Day 3: Install packages

## 1. Install packages by conda

In this tutorial series, we are using conda. Conda not only can manage virtual environments like we did in [Day 1](day1.md) but also can manage the *packages* installed in each environment. 

Python is known as a "battery-included" language: the default Python already contains many useful functionalities (like math, HTTP communication, etc) out of the box as the standard library. 

However, there are many third-party libraries to further extend the functions of Python. These are distributed as *packages*. 

To install a package using conda, go into the environment to which you want to install the package. In Anaconda Prompt (or Terminal in Mac), run

    conda activate my_first_env

Then run

    conda install numpy

This will install the [NumPy](https://numpy.org/) package. You will be prompted to confirm the installation before it actually starts installing. 

Note that the package is installed only in the current environment. 

## 2. Packages needed in this tutorial series

- [NumPy](https://numpy.org/)
- [SciPy](https://scipy.org/)
- [Matplotlib](https://matplotlib.org/)
- [hicsv-python](https://github.com/shntrnkgw/hicsv)

To install everything at once, `conda activate` the target environment and then

    conda install -c conda-forge numpy scipy matplotlib hicsv-python

Here, `-c conda-forge` is added to search for the packages in `conda-forge` repository. You will notice that conda installs other packages that are required by these four packages automatically. 

## 3. Verify that the packages are installed and ready

You can easily confirm the installation by `import`ing them in Python. In Anaconda Prompt (Terminal on Mac), run

    python

Then after a while you will see `>>>` at the last line. You are now in the interactive mode of Python. Type 

    import numpy

and press Enter. If `>>>` appears in the next line without error messages, it's OK. You can try with other packages. 

    import scipy
    import matplotlib
    import hicsv

You can notice that even if you installed `hicsv-python` package, what you `import` is `hicsv`. Actually, `hicsv` is a *module* in the package. But these terms are often not strictly used. 

To exit from the interactive Python interpreter, 

    exit()


## 4. Notes

Python comes with the default package manager called pip. You can also install packages via pip. However, using both conda and pip will lead to confusion. The best practice with conda is 
- Always install packages via conda whenever possible. 
- **Only when the package is not available in conda repositories**, install it via pip or by other methods, after all other packages have been installed via conda. 

## Appendix: packages that are not needed in this tutorial series but useful

- [openpyxl](https://openpyxl.readthedocs.io/en/stable/) - Read and manipulate Microsoft Excel spreadsheets
- [uncertainties](https://pythonhosted.org/uncertainties/) - Error calculation