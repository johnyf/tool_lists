# Python optimization frameworks

## General
- [`cvxopt`](https://github.com/cvxopt/cvxopt)
- [Pyomo](https://software.sandia.gov//trac/coopr/wiki/Pyomo) (Python) (Sandia)
- [PuLP](https://pypi.python.org/pypi/PuLP/1.5.6) (Python) interfaces to GLPK, CLP/CBC, CPLEX, GUROBI
- [`optlang`](https://github.com/biosustain/optlang)
- [PICOS](http://picos.zib.de/index.html) (GPL-3, Python): interface to linear and conic optimization solvers (cvxopt, smcp, mosek, cplex, gurobi, zibopt)
- [`pycplex`](https://code.google.com/p/pycplex/) (MIT, Python, C): interface to the ILOG CPLEX® Callable Library
- [python-zibopt](https://code.google.com/p/python-zibopt/) (GPL-3, Python): solve MIQP using SCIP and SoPlex from the ZIB Optimization Suite
- [SCIP](http://scip.zib.de/) (ZIB): MIP and MINLP

- [COIN-OR](http://www.coin-or.org/projects/): index of packages interfacing to solvers
- [IPOPT](https://projects.coin-or.org/Ipopt): large-scale nonlinear opt
	- [`pyipopt`](https://code.google.com/p/pyipopt/) (Python): interface to IPOPT
- [NLOPT](http://ab-initio.mit.edu/wiki/index.php/NLopt): nonlinear opt lib with Python bindings
- [lpsolve](http://lpsolve.sourceforge.net/5.5/Python.htm)

## GLPK
- [PyGLPK](https://pypi.python.org/pypi/glpk/0.3)
- [`swiglpk`](https://pypi.python.org/pypi/swiglpk/0.1.0): plain vanilla swig bindings to GLPK `C` library
- [`epyglpki`](https://github.com/equaeghe/epyglpki/) (Cython)
- [`python-glpk`](http://www.dcc.fc.up.pt/~jpp/code/python-glpk/) (GPL-2)
- [`ecyglpki`](https://github.com/equaeghe/ecyglpki) (-, GPL-3): `Cython` interface
- [`ctypes-glpk`](https://code.google.com/p/ctypes-glpk/) (Python, GPL-3): ctypes interface
- [PyMathProg](http://pymprog.sourceforge.net/) (Python) AMPL reincarnation, connects to GLPK via PyGLPK

## Modeling
- [`cvexp`](https://pypi.python.org/pypi/cvexp/0.1) (Python) interfaces to GLPK, `cvxopt`
- [`cvxpy`](https://github.com/cvxgrp/cvxpy) (Python): on top of `cvxopt`
- [PyLMI-SDP](https://pypi.python.org/pypi/PyLMI-SDP/0.2) (BSD, Python): set of classes to represent and manipulate LMIs symbolically using SymPy. It also includes tools to export LMIs to CVXOPT SDP input and to the SDPA format

## Polytopic computational geometry
- [`polytope`](https://github.com/tulip-control/polytope) (BSD-3, Python): uses `cvxopt`
- [PyPolyhedron](LGPL, Python, C): PyPolyhedron is a Python interface to a C-library cddlib