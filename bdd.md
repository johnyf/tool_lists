**Table of Contents**

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Python](#python)
- [Ruby](#ruby)
- [LISP](#lisp)
- [CWEB](#cweb)
- [C](#c)
- [C#](#c)
- [Clojure](#clojure)
- [Java](#java)
- [Javascript](#javascript)
- [Julia](#julia)
- [ML](#ml)
- [OCaml](#ocaml)
- [Haskell](#haskell)
- [Isabelle/HOL](#isabellehol)
- [Prolog](#prolog)
- [Lua](#lua)
- [Erlang](#erlang)
- [Rust](#rust)
- [PHP](#php)
- [other](#other)
- [Unsorted](#unsorted)
- [Abbreviations](#abbreviations)

<!-- /TOC -->

# Python
- [dd](https://github.com/johnyf/dd) (BSD-3, Python):
    - BDD and MDD pure Python implementation
    - Cython interface to BDDs and ZDDs of CUDD in `dd.cudd`
    - Cython interface to BDDs of Sylvan in `dd.sylvan`
    - Cython interface to BDDs of BuDDy in `dd.buddy`
- [pyEDA](https://github.com/cjdrake/pyeda/blob/master/pyeda/boolalg/bdd.py) (BSD, Python): BDD implementation without a BDD manager
- [PyCUDD](https://bears.ece.ucsb.edu/pycudd.html) (BSD-3, Python): SWIG-generated bindings to CUDD
    - [rePyCUDD](https://github.com/pysmt/repycudd): reentrant version
    - [PyCUDD packaging](https://github.com/aur-archive/pycudd)
- `marduk` in [RATSY](http://rat.fbk.eu/ratsy/) (LGPL, Python): Wrappers of NuSMV (which uses CUDD) (TU Graz)
    - [`marduk/src/bddwrap.py`](https://github.com/johnyf/marduk/blob/master/bddwrap.py): Wraps BDD manager
    - [`marduk/src/zddwrap.py`](https://github.com/johnyf/marduk/blob/master/zddwrap.py): Wraps ZDD manager
- [mccarthy-to-bryant](https://github.com/darius/mccarthy-to-bryant) (GPL-3, Python) (mainly educational)
- [PBDD](https://github.com/tyler-utah/PBDD) (BSD, Python) (mainly educational)
- [robdd](https://github.com/ericvoid/robdd) (?, Python)
- [`py-ydd`](https://github.com/kyouko-taiga/py-ydd) (Apache-2, Python/C++): YDDs (Yet another Decision Diagram), a data structure that allows to efficiently store extremely large families of sets, and perform various operations on them quiete efficiently.
- [Graphillion](https://github.com/takemaru/graphillion) (MIT, Python/C++): Graphset operations library using TdZDD

# Ruby
- [CUDD-rb](https://github.com/blambeau/cudd-rb) (MIT, Ruby): bindings to CUDD
- [Ruby-BDD](https://people.cs.aau.dk/~adavid/BDD/): bindings to Buddy

# LISP
- [CL-CUDD](https://github.com/Neronus/CL-CUDD) (Lisp, BSD): bindings to CUDD
- [`trivialib.bdd`](https://github.com/guicho271828/trivialib.bdd) (Common Lisp, LLGPL): Functional implementation of BDDs and ZDDs (Univ. of Tokyo)
- [clj-bdd](https://github.com/dcreager/clj-bdd) (EPL, Clojure)
- [`bdd`](https://github.com/rhinocratic/bdd) (EPL, Clojure)

# CWEB
- [`bdd14.w`](http://www-cs-faculty.stanford.edu/~uno/programs/bdd14.w): BDD package by Donald Knuth
- [`bdd15.w`](http://www-cs-faculty.stanford.edu/~uno/programs/bdd15.w): ZDD package by Donald Knuth

# C
- [CUDD](http://vlsi.colorado.edu/~fabio/CUDD/) (BSD): (Colorado U)
    - [EXTRA](https://people.eecs.berkeley.edu/~alanmi/research/extra/) [v2.0](https://people.eecs.berkeley.edu/~alanmi/research/extra/extra20a.tar.gz), [v1.3](https://people.eecs.berkeley.edu/~alanmi/research/extra/extra13.tar.gz)(?, C): extends the functionality of CUDD, contains additional {A,B,Z}DD operators and routines, most of the code is meant to enhance the manipulation of ZDDs (UC Berkeley)
    - [DDDMP](http://fmgroup.polito.it/quer/research/tool/tool.htm) (BSD): Decision Diagram DuMP package
    - [CUDDaux](https://pop-art.inrialpes.fr/people/bjeannet/mlxxxidl-forge/cuddaux/index.html) (LGPL-2.1, [C](https://github.com/thizanne/mlcuddidl/blob/master/cuddaux.h)): library that implements additional ADD functions for CUDD ([INRIA](https://pop-art.inrialpes.fr/~bjeannet/))
    - [cnf2obdd](http://www.sd.is.uec.ac.jp/toda/code/cnf2obdd.html) (same as MiniSAT)
    - [windows port](https://github.com/lpradel/CUDDVC-2.5.0)
    - [Chain-CUDD](https://github.com/rebryant/Chain-CUDD) (BSD-3, C): Extension of CUDD to support BDD with chain nodes
    - [Cloud-BDD](https://github.com/rebryant/Cloud-BDD) (?, C): Distributed implementation of BDD package, using CUDD
    - [SimpleCUDD](https://limo.libis.be/primo-explore/fulldisplay?docid=LIRIAS1652866&context=L&vid=Lirias&search_scope=Lirias&tab=default_tab&lang=en_US) (Artistic License 2.0, C): A simplified fast interface for the use of CUDD for Binary Decision Diagrams
    - Python:
        - `dd.cudd`
        - PyCUDD
        - `marduk`
    - Ruby:
        - CUDD-rb
    - LISP:
        - CL-CUDD
    - OCaml:
        - MLCuddIDL
    - Haskell:
        - hBDD
        - hs-cudd
        - Haskell-CUDD
    - Java:
        - JBDD
        - Jedd
    - C\#:
        - PAT.BDD
    - Prolog:
        - swipl_cudd
    - Rust:
        - `cudd_rust`
- [BuDDy](https://sourceforge.net/projects/buddy/) (Public domain): (UMichigan)
    - [fork](https://github.com/utwente-fmt/buddy) UTwente
    - [fork](https://github.com/jjgreen/rebuddy): re-entrant version
    - [`libbdd-dev`](https://packages.debian.org/jessie/libbdd-dev): Debian Linux package
    - Python:
        - `dd.buddy`
    - ML:
        - `muddy`
    - OCaml:
        - `ocaml-buddy`
    - Java:
        - JBDD
    - Ruby:
        - Ruby-BDD
    - C\#
        - BuDDySharp
- [Cal BDD](http://embedded.eecs.berkeley.edu/Research/cal_bdd/) (BSD): (UC Berkeley)
- [ABCD](http://fmv.jku.at/abcd/) (?): (JKU)
- [CMU BDD](https://www.cs.cmu.edu/afs/cs/project/modck/pub/www/bdd.html): (CMU)
    - hBDD
- Geert Janssen: package [used in PVS](https://github.com/samowre/PVS/tree/master/BDD/bdd) and available here: ftp://ftp.ics.ele.tue.nl/pub/users/geert/ (Eindhoven)
- [MONA](http://bdd.hpi.uni-potsdam.de/mona.html)
- [TiGeR](http://www.cs.cmu.edu/~bwolen/fmcad98/packages/tiger/tgrlib/refman.html) (C): BDDs and compacted Boolean functions (DEC)
- [PPBF](http://www.cs.cmu.edu/~bwolen/software/) (C): parallel BDD package based on partial BFS expansion (CMU)
- [Sylvan](https://github.com/trolando/sylvan) (Apache-2): Multi-core library using work-stealing framework and lock-less hash table
    - Python:
        - dd
    - Haskell:
        - Sylvan-Haskell
    - Java:
        - jSylvan
        - cpachecker
    - C\#
        - SylvanSharp
- [MEDDLY](https://asminer.github.io/meddly/) ([also](http://meddly.sourceforge.net/)) (LGPLv3, [C++](https://github.com/asminer/meddly)): Multi-terminal and Edge-valued Decision Diagram LibrarY, including BDDs (Iowa State Univ.)
- [libDDD](https://lip6.github.io/ITSTools-web/libddd.html) (LGPLv3, [C++](https://github.com/lip6/libDDD)): integer-valued data decision diagrams and hierarchical set decision diagrams (LIP6, Sorbonne Univ., CNRS)
- [TdZdd](https://github.com/kunisura/TdZdd) (MIT, C++): top-down breadth-first  n-ary DD/ZDD manipulation, parallel processing with OpenMP
- [CacBDD](http://www.kailesu.net/CacBDD/) (BSD-3, C++)
- [BDDSharp](https://github.com/ancailliau/BDDSharp) (MIT, C\#): (U Catholique Louvain)
- [LaVaBDD](http://www.ulb.ac.be/di/ssd/nmaquet/lavabdd/0.4/doc/index.html) (?, C++): Lattice-valued BDDs (ULB)
- [`wld`](https://ira.informatik.uni-freiburg.de/software/wld/) (FUSC, C++): word-level DDs (UFreiburg)
- [BDS](http://www.ecs.umass.edu/ece/labs/vlsicad/bds/bds.html) (FUSC, C): (UMass)
- [Biddy](https://github.com/meolic/biddy) (GPL-2, C): a multi-platform academic BDD [package](https://biddy.meolic.com) (UMaribor)
- [list](http://bdd.hpi.uni-potsdam.de/packages.html) of BDD packages with comparisons
- [BBDD](http://lsi.epfl.ch/cms/page-102597.html) (?, ?): biconditional BDDs
- [RicBDD](https://github.com/ric2k1/RicBDD) (GPL, C++)
- [LiBDD](https://github.com/vmikhav/liBDD) (BSD, C): multi-platform BDDs package
- [BDDC](http://www-verimag.imag.fr/~raymond/tools/bddc/manual/index.html): BDD-based logical calculator
- [EHV](http://www.cs.cmu.edu/~bwolen/fmcad98/packages/ehv.html): Eindhoven BDD package
- [`libvata/src/mtbdd`](https://github.com/ondrik/libvata/tree/master/src/mtbdd) (C++, GPL-3)
- [zddfun](https://github.com/blynn/zddfun) (?, C): Logic puzzle solvers using ZDDs, inspired by TAOCP 4.1
- [ZDD](https://github.com/tanakalab/ZDD) (?, C++): Multi-terminal ZDDs

# C# #
- [PAT BDD library](https://www.comp.nus.edu.sg/~pat/bddlib/) (?, C\#): BDD library for symbolic model checking of hierarchical systems, with a C\# interface to CUDD version 2.4.2
- [SylvanSharp](https://github.com/thisiscam/SylvanSharp) (?, C\#): bindings to Sylvan
- [BuDDySharp](https://github.com/thisiscam/BuDDySharp) (?, C\#): bindings to BuDDy

# Clojure
- [clj-bdd](https://github.com/dcreager/clj-bdd) (EPL, Clojure)
- [bdd](https://github.com/rhinocratic/bdd) (EPL)

# Java
- [JavaBDD](http://javabdd.sourceforge.net/) (GPL-2 or LGPL-2, Java)
- [JDD](http://javaddlib.sourceforge.net/jdd/) (zlib, [Java](https://bitbucket.org/vahidi/jdd)): BDD and ZDD support, inspired by Buddy
- [JBDD](http://javaddlib.sourceforge.net/jbdd/) (zlib, [Java](https://bitbucket.org/vahidi/jbdd/src/master/)): bindings to CUDD, Buddy
- [BeeDeeDee](https://github.com/JuliaSoft/BeeDeeDee) (GPL-2, Java): Multi-thread library
- [LightBDD](https://github.com/SigmaX/LightBDD) (?, Java): simple library
- [jSylvan](https://github.com/utwente-fmt/jsylvan) (Apache-2, C/C++/Java): JNI bindings for Sylvan
- [cpachecker](https://github.com/dbeyer/cpachecker/tree/c25691b2328ea05071c6950d02bf72b20ad81ed0/src/org/sosy_lab/cpachecker/util/predicates/bdd) (Apache-2, Java): Java bindings for Sylvan
- [JADE](https://www.informatik.uni-bremen.de/agra/eng/jade.php) (custom, Java) (UFreiburg)
- [JINC](http://jossowski.de/projects/jinc/jinc.html) (GPL-2, C++): utilizes multi-threading, has BDD, ADD, NADD, ZADD, TADD, MDD (UBonn)
- [djbdd](https://github.com/diegojromerolopez/djbdd) (Java 7, GPL-3)
- [Java applet](http://tams-www.informatik.uni-hamburg.de/applets/java-bdd/bdd-applet.html) (?, Java) (UHamburg)
- [SableJBDD](http://www.sable.mcgill.ca/~fqian/SableJBDD/) (LGPL): (McGill Univ.)
- [Jedd](https://www.sable.mcgill.ca/jedd/) (Java, LGLPL-2): Java Extension for Decision Diagrams based on the polyglot framework, supports as backends: CUDD, BuDDy, SableJBDD, JavaBDD
- [zdd_java](https://github.com/higotakayuki/zdd_java): educational ZDD implementation
- [HumbleBDD](https://github.com/powerofpi/HumbleBDD) (MIT, Java): BDDs, ZDD

# Javascript
- [binary decision diagram](https://github.com/pubkey/binary-decision-diagram) (Apache-2, JavaScript): A library to create, minimize and optimize binary decision diagrams
- [BDD](http://fooo.fr/~vjeux/epita/bdd/) (?, Javascript)

# Julia
- [BinaryDecisionDiagrams](https://github.com/albertocasagrande/BinaryDecisionDiagrams) (MIT, Julia)
- [`ZDDs.jl`](https://github.com/ngr-t/ZDDs.jl) (MIT, Julia)

# ML
- [`muddy`](https://github.com/kfl/muddy) (MIT, ML): bindings to Buddy ([older home](http://www.itu.dk/research/muddy/)) (UCopenhagen)

# OCaml
- [DAGaml](https://gitlab.com/boreal-ldd/dagaml) (LGPL-3.0, OCaml): implements various models of BDD, such as ROBDD, ZDD, etc. and some more experimental ones
- [MLCuddIDL](https://pop-art.inrialpes.fr/~bjeannet/mlxxxidl-forge/mlcuddidl/) (LGPL-2.1, [C/OCaml](https://framagit.org/nberth/mlcuddidl)): bindings to CUDD ([INRIA](https://pop-art.inrialpes.fr/~bjeannet/))
  - [OPAM entry](https://opam.ocaml.org/packages/mlcuddidl/) of `mlcuddidl`
  - [mirror](https://github.com/thizanne/mlcuddidl) of `mlcuddidl`
- [`ocaml-cudd`](https://github.com/romainbrenguier/ocaml-cudd) (GPLv2, OCaml/C): bindings to CUDD
- [`ocaml-buddy`](https://github.com/abate/ocaml-buddy) (LGPL, OCaml): bindings to Buddy ([Paris 7](http://mancoosi.org/~abate/about-me))
  - [OPAM entry](https://opam.ocaml.org/packages/ocaml-buddy/) of `ocaml-buddy`
- [MLBDD](https://github.com/arlencox/mlbdd) (MIT, OCaml): includes garbage collection, complemented edges
  - [OPAM entry](https://opam.ocaml.org/packages/mlbdd/) of `mlbdd`
- [`Symbolickat.bdd`](https://perso.ens-lyon.fr/damien.pous/symbolickat/safa.docdir/Bdd.html) (?, OCaml): pure-OCaml library ([ENS de Lyon](https://perso.ens-lyon.fr/damien.pous/))
- [John Harrison](https://www.cl.cam.ac.uk/~jrh13/atp/OCaml/bdd.ml) (BSD-3, Ocaml)
- [Jean-Christophe Filliatre](https://www.lri.fr/~filliatr/ftp/ocaml/bdd/) (GPL-2, Ocaml)
- [`xlasat`](https://gforge.inria.fr/scm/viewvc.php/attic/xlsat/?root=sodiac) (? , Ocaml) (INRIA)
- [OcamlBdd](http://www.linux-france.org/~dmentre/code/OcamlBdd.tar.gz)

# Haskell
- [hBDD](https://github.com/peteg/hBDD) (GPL-2, Haskell): bindings to CUDD and CMU-BDD ([Australian National Univ.](https://peteg.org/))
- [hs-cudd](https://github.com/bradlarsen/hs-cudd) (BSD-3, Haskell): bindings to CUDD ([Veracode](http://bradford-larsen.net/))
- [Haskell-CUDD](https://github.com/adamwalker/haskell_cudd) (BSD-3, Haskell): bindings to CUDD ([NICTA](https://github.com/adamwalker))
- [HasCacBDD](https://github.com/m4lvin/HasCacBDD) (GPL-2, Haskell): bindings to CacBDD (ILLC, University of Amsterdam)
- [Sylvan-Haskell](https://github.com/adamwalker/sylvan-haskell) (BSD-3, Haskell/C): bindings to Sylvan ([NICTA](https://github.com/adamwalker))
- [`termite2.bdd`](https://github.com/termite2/bdd) (?, Haskell): BDD abstraction layer (NICTA)
- [`robbed`](https://github.com/travitch/robbed) (BSD-3, Haskell): ([Galois](https://nochair.net/))
- [haskell-obdd](https://github.com/jwaldmann/haskell-obdd) (GPL-2, Haskell): ([Leipzig Univ. for Applied Sciences](http://www.imn.htwk-leipzig.de/~waldmann/))
- [`robdd`](https://github.com/slava-sh/robdd) (BSD-3, Haskell)
- [`bdd`](https://github.com/hguenther/bdd) (BSD-3, Haskell)
- [`robdd`](https://github.com/johnpmayer/robdd) (?, Haskell)
- [ZDD](https://github.com/mg50/ZDD) (MIT, Haskell)

# Isabelle/HOL
- [`bdd`](https://github.com/jcaesar/bdd) (BSD, Isabelle/HOL/Haskell): verified and executable implementation of ROBDDs in Isabelle/HOL, [archived proofs](https://www.isa-afp.org/entries/ROBDD.shtml) ([TUM](https://liftm.de/))

# Prolog
- [`swipl_cudd`](https://github.com/lagoonv/swipl_cudd) (?, C/Prolog): bindings to CUDD
- [`upbdd`](https://github.com/vale1410/upbdd) (?, Prolog/C++): UP-BDD data structure implementation

# Lua
- [mccarthy-to-bryant/lua](https://github.com/darius/mccarthy-to-bryant/tree/master/lua) (GPL-3, Lua)
- [`lua-bdd`](https://github.com/silentbicycle/lua-bdd) (BSD, Lua)

# Erlang
- [seqbdd](https://github.com/shu-den/seqbdd) (BSD-like, Erlang): Sequence BDD data structure

# Rust
- [`boolean_expressions`](https://github.com/cfallin/boolean_expression) (MIT, Rust): BDD implementation, conversion from/to formulae with cubelist-based minimization
- [`cudd_rust`](https://github.com/malie/cudd_rust) (BSD-3, Rust): bindings to CUDD

# PHP
- [BDD](https://github.com/andreaswolf/BinaryDecisionDiagrams) (?, PHP)

# other
- [BDD papers, links](http://web.cecs.pdx.edu/~alanmi/research/dd/bddLinks.htm#BDDPackages)

# Unsorted
- [QuIDDPro](http://vlsicad.eecs.umich.edu/Quantum/qp/index.html)
- [BDS](http://ddd.fit.cvut.cz/prj/BDS/index.php?page=main)
- [EVMDD](https://github.com/siminice/EVMDD)
- [ZBDD](https://www.aloul.net/Tools/zbddLib/)
- [`libsdd`](https://github.com/ahamez/libsdd)

# Abbreviations
- BDD = Binary Decision Diagrams
- ZDD = Zero-suppressed BDD
