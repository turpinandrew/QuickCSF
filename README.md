# QuickCSF

A fast, adaptive approach to estimating contrast sensitivity function parameters.

This implementation is based on:

> Lesmes, L. A., Lu, Z. L., Baek, J., & Albright, T. D. (2010). Bayesian adaptive estimation of the contrast sensitivity function: The quick CSF method. *Journal of vision*, 10(3), 17-17.

Special thanks to Dr. Tianshi Lu at Wichita State University for providing a Matlab implementation of the fundamental algorithm and Dr. Rui Ni at Wichita State University for the motivation.

Peripheral CSF based on 

> Rosén, R., Lundström, L., Venkataraman A.P., Winter, S., Unsbo, P. (2014).
	Quick contrast sensitivity measurements in the periphery.
	Journal of Vision July 2014, Vol.14, 3. doi:https://doi.org/10.1167/14.8.3

Thanks to Prof. Andrew Turpin at Lions Eye Institute, Australia, for incorporating the peripheral parameterisation into our code and providing the noQT option..

## Dependencies
~~~~
$ pip3 install -e .
~~~~
Requires:
* `numpy`
* `qtpy` (not necessary for simulation)
* Qt bindings (via `PySide2`, `PyQt5`, `PySide`, or `PyQt`)
* `matplotlib`

## Usage
### Measuring CSF
Run:
~~~bash
$ python -m QuickCSF.app
~~~
A settings dialog will appear; session ID and viewing distance are required. Arguments can also be specified on the command line. Use the `--help` flag to see all options:
~~~bash
$ python -m QuickCSF.app --help
~~~

### Simulate and visualize an evaluation
Run:
~~~bash
$ python -m QuickCSF.simulate
~~~
A settings dialog will appear; the number of trials is required. Arguments can also be specified on the command line. use the `--help` flag to see all options:
~~~bash
$ python -m QuickCSF.simulate --help
~~~

As an example for a command line version that does not use `qtpy`
~~~bash
$ python -m QuickCSF.simulate --noQT --periphery -minf 1 -maxf 50 -fr 50 -cr 64 -s 27 -d 20 -b 10 -perfect -n 200 
~~~