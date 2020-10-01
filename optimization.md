# Python optimization frameworks

## General
- [`cvxopt`](https://github.com/cvxopt/cvxopt) (GPLv3, Python/C): Python Software for Convex Optimization
- [Pyomo](https://software.sandia.gov//trac/coopr/wiki/Pyomo) (Python) (Sandia)
- [PuLP](https://pypi.python.org/pypi/PuLP/1.5.6) (Python) interfaces to GLPK, CLP/CBC, CPLEX, GUROBI
- [`optlang`](https://github.com/biosustain/optlang)
- [PICOS](http://picos.zib.de/index.html) (GPL-3, Python): interface to linear and conic optimization solvers (cvxopt, smcp, mosek, cplex, gurobi, zibopt)
- [`pycplex`](https://code.google.com/p/pycplex/) (MIT, Python, C): interface to the ILOG CPLEX® Callable Library
- [python-zibopt](https://code.google.com/p/python-zibopt/) (GPL-3, Python): solve MIQP using SCIP and SoPlex from the ZIB Optimization Suite
- [SCIP](https://www.scipopt.org) (ZIB, C): MIP and MINLP, and a framework for constraint integer programming and branch-cut-and-price
    - [PySCIPOpt](https://github.com/SCIP-Interfaces/PySCIPOpt) (MIT, Python): Python interface for the SCIP Optimization Suite
    - [SCIP.jl](https://github.com/SCIP-Interfaces/SCIP.jl) (MIT, Julia): Julia interface to SCIP solver
    - [JSCIPOpt](https://github.com/SCIP-Interfaces/JSCIPOpt) (MIT, Java/C): Java interface for the SCIP Optimization Suite
- [COIN-OR](http://www.coin-or.org/projects/): index of packages interfacing to solvers
- [BONMIN](https://www.coin-or.org/Bonmin/) (EPL-1.0, C++): Basic Open-source Nonlinear Mixed INteger programming, for solving general MINLP (Mixed Integer NonLinear Programming) problems (IBM, CMU)
- [IPOPT](https://projects.coin-or.org/Ipopt): large-scale nonlinear opt
	- [`pyipopt`](https://code.google.com/p/pyipopt/) (Python): interface to IPOPT
- [NLOPT](http://ab-initio.mit.edu/wiki/index.php/NLopt): nonlinear opt lib with Python bindings
- [lpsolve](http://lpsolve.sourceforge.net/5.5/Python.htm)
- [NEOS Server](https://neos-server.org): State-of-the-Art Solvers for Numerical Optimization: free internet-based service for solving numerical optimization problems
- [Numberjack](https://github.com/eomahony/Numberjack): (LGPL-2.1, C++/Python) combinatorial optimisation platform
- [NOMAD](https://www.gerad.ca/nomad/): (LGPL, C++): implementation of the Mesh Adaptive Direct Search algorithm (MADS), designed for difficult blackbox optimization problems, with objective and constraints arising from costly computer simulations
- [PyMUMPS](https://github.com/bfroehle/pymumps) (BSD-3, Python): A parallel sparse direct solver

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
- https://github.com/cvxgrp/qcml
- [PyLMI-SDP](https://pypi.python.org/pypi/PyLMI-SDP/0.2) (BSD, Python): set of classes to represent and manipulate LMIs symbolically using SymPy. It also includes tools to export LMIs to CVXOPT SDP input and to the SDPA format

## Polytopic computational geometry
- [`polytope`](https://github.com/tulip-control/polytope) (BSD-3, Python): Geometric operations on polytopes of any dimension, using `scipy`, or `cvxopt` if present
- [`transforms3d`](https://github.com/matthew-brett/transforms3d) (BSD-2, Python): 3 dimensional spatial transformations
- [PyPolyhedron](https://anaconda.org/pierre-haessig/pypolyhedron) (LGPL, Python, C): Python interface to the C-library `cddlib`
- [`geode`](https://github.com/otherlab/geode) (BSD-3, C++/Python): A computational geometry library for C++ and Python ([Otherlab](https://otherlab.com/))
- [MinkSum](https://sites.google.com/site/christopheweibel/research/minksum) (GPLv2, C++): takes as input the vertices of a set of polytopes and outputs the vertices of their Minkowski sum (Google)

## Zonotopes
- [`libzonotope`](https://github.com/vindvaki/libzonotope) (MIT, C++/Python): a collection of scripts and algorithms for zonotope manipulations

## abbreviations
- MIP: Mixed Integer Programming
- MILP: Mixed Integer Linear Programming
- MINLP: Mixed Integer Nonlinear Programming
