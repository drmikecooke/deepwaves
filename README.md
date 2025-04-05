# deepwaves
Binder repo of deep wave work: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/drmikecooke/deepwaves.git/HEAD)

This work is inspired by John D. Fenton's work available at [https://johndfenton.com/](https://johndfenton.com/). In particular I have generated comparisons with Fenton's [Fourier.exe](https://johndfenton.com/Steady-waves/Fourier.html) running in a microsoft environment with a "Data.dat" file of the form:

```{code}
Test deep-water wave - use negative H/L
-0.12 -H/L
Wavelength	Measure of length: for infinite depth, only "Wavelength"
0 	Value of that length: Meaningless for deep water
1		Current criterion (1 or 2)
0.0		Current magnitude, (dimensionless with respect to g and measure of length)
20		Number of Fourier components
60		Number of height steps to reach solution
FINISH
```

The second line was varied between "-0.01 -H/L" and "-0.12 -H/L". The large number of height steps (60) was found necessary to converge the -0.11 variant &mdash; this can be reduced to 20 for the other values (including 0.12). The results in the generated "Solution.res" file was renamed to a "txt" file (Jupyter does not seem to allow viewing of the .dat and .res files since they are not officially in a UTF-8 format although they seem to be plain ASCII, may be something to do with difference between microsoft and the linux system I use for coding).

The txt files in the "deep" directory are also labeled with the H/L (height/wavelength) times 100.

My code is based mainly on [Fenton, J. D. (1999) Numerical methods for nonlinear waves](https://johndfenton.com/Papers/Fenton99Liu-Numerical-methods-for-nonlinear-waves.pdf), and the Instructions pdf that comes with Fenton's Fourier.exe. I have avoided the need to get involved with Newton-Raphson root finding, Jacobians, and height stepping (at least for deep waves) by using scipy's hybrid root finder.

## Contents

1. deep directory: Contains Fenton results
2. Fenton-mywork.ipynb: Comparison of my code with Fenton results
