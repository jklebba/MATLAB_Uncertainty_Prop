# MATLAB_Uncertainty_Prop
This repo contains three stand-alone functions for uncertainty propagation in MATLAB & GNU Octave. 

Two of the functions use the regular uncertainity propagation [formula](https://en.wikipedia.org/wiki/Propagation_of_uncertainty#Non-linear_combinations) while the
third uses Monte Carlo simulation. Monte Carlo is more accurate when the function which error is propagated through is nonlinear or when the resulting uncertainity distribution is nonnormal.

The functions are unique in that each one can handle correlated as well as uncorrelated uncertainties. The Monte Carlo function **propUncertMC()** also supports many different types of distributions, truncated distributions, custom data inputs, and various additional methods for generating Monte Carlo samples.

#### propUncertSym()
* Uses the [standard formula](https://en.wikipedia.org/wiki/Propagation_of_uncertainty#Non-linear_combinations) for uncertainity propagation.
* Calculates the derivatives in the formula using the MATLAB/Octave's symbolic package.
* Can handle correlated or uncorrelated uncertainties.

#### propUncertCD()
* Uses the [standard formula](https://en.wikipedia.org/wiki/Propagation_of_uncertainty#Non-linear_combinations) for uncertainity propagation.
* Approximates the derivatives in the formula using a central difference approximation.
* Can handle correlated or uncorrelated uncertainties.

#### propUncertMC()
* Uses Monte Carlo simulation to propagate uncertainity.
* Supports most/all of the distribution types in MATLAB's statistics and machine learning toolbox, including truncated distributions.
* Can generate correlated samples from any combination of distribution types via a gaussian copula approach with iterative optimization of the correlation parameters.
* Supports custom data inputs and various methods for generating Monte Carlo samples such as bootstrapping and distribution fitting.
* Allows for visualization of the uncertainty distributions using histogram plots.

## Usage 
Explanations of syntax and simple examples of each function's usage are included in the comments of each function file. More detailed examples can be found in the included file 'uncert_prop_examples.m'.

When using propUncertMC() it is recommended to set the parameter for the number of samples 'N' as high as possible while still maintaining an acceptable runtime.

## Todo
Make the following features of propUncertMC() compatible with GNU Octave
* Sampling of distributions types besides normal and uniform
* Distribution fitting 
* Correlated sample generation 
