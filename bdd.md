# Python
- [dd](https://github.com/johnyf/dd) (BSD-3, Python): BDDs in pure Python
- [pyEDA](https://github.com/cjdrake/pyeda/blob/master/pyeda/boolalg/bdd.py): mature, maintained

- [PyCUDD](http://bears.ece.ucsb.edu/pycudd.html) (?, Python): SWIG-generated bindings to CUDD
	* [rePyCUDD](https://github.com/pysmt/repycudd): reentrant version
- [`marduk/src/bddwrap.py`](http://rat.fbk.eu/ratsy/) (LGPL, Python): Wraps BDD manager in NuSMV (which uses CUDD) (TU Graz)

- [py-simple-bdd](https://code.google.com/p/py-simple-bdd/): unmaintained, "exercise to learn python"
- [PBDD](https://github.com/tyler-utah/PBDD)
- [robdd](https://github.com/ericvoid/robdd)
- [ROBDD](https://github.com/conix-security/springbok/tree/master/ROBDD): misc subpackage (same as above)
- [EasyBDD](https://github.com/utisam/EasyBDD): mainly graph class with ITE and custom parser

# Ruby
- [CUDD-rb](https://github.com/blambeau/cudd-rb) (MIT, Ruby): bindings to CUDD
- [Ruby-BDD](http://people.cs.aau.dk/~adavid/BDD/): bindings to Buddy

# LISP
- [CL-CUDD](https://github.com/Neronus/CL-CUDD) (Lisp, BSD): bindings to CUDD
- [clj-bdd](https://github.com/dcreager/clj-bdd) (EPL, Clojure)
- [`bdd`](https://github.com/rhinocratic/bdd) (EPL, Clojure)

# C
- [CUDD](http://vlsi.colorado.edu/~fabio/CUDD/) (BSD): (Colorado U)
	- [windows port](https://github.com/lpradel/CUDDVC-2.5.0)
	- PyCUDD
	- CUDD-rb
	- CL-CUDD
	- hBDD
	- hs-cudd
	- Haskell-CUDD
	- JBDD
	- PAT.BDD
	- swipl_cudd
- [DDDMP](http://fmgroup.polito.it/quer/research/tool/tool.htm) (BSD): Decision Diagram DuMP package
- [BuDDy](https://sourceforge.net/projects/buddy/) (Public domain): (UMichigan)
	- `muddy`
	- `ocaml-buddy`
	- [fork](https://github.com/utwente-fmt/buddy) UTwente
	- [fork](https://github.com/jjgreen/rebuddy): re-entrant version
	- JBDD
	- Ruby-BDD
- [Cal BDD](http://embedded.eecs.berkeley.edu/Research/cal_bdd/) (BSD): (UC Berkeley)
- [ABCD](http://fmv.jku.at/abcd/) (?): (JKU)
- [CMU BDD](http://www.cs.cmu.edu/afs/cs/project/modck/pub/www/bdd.html): (CMU)
	- hBDD
- Geert Janssen: package [used in PVS](https://github.com/samowre/PVS/tree/master/BDD/bdd) and available here: ftp://ftp.ics.ele.tue.nl/pub/users/geert/ (Eindhoven)
- [MONA](http://bdd.hpi.uni-potsdam.de/mona.html)
- [TiGeR](http://www.cs.cmu.edu/~bwolen/fmcad98/packages/tiger/tgrlib/refman.html) (C): BDDs and compacted Boolean functions (DEC)
- [PPBF](http://www.cs.cmu.edu/~bwolen/software/) (C): parallel BDD package based on partial BFS expansion (CMU)
- [Sylvan](https://github.com/trolando/sylvan) (Apache-2): Multi-core library using work-stealing framework and lock-less hash table
	- Sylvan-Haskell
	- jSylvan
	- cpachecker
- [libDDD](http://move.lip6.fr/software/DDD/) (LGPL, C++): (CNRS)
- [TdZdd](https://github.com/kunisura/TdZdd) (MIT, C++): top-down breadth-first  n-ary DD/ZDD manipulation, parallel processing with OpenMP
- [CacBDD](http://www.kailesu.net/CacBDD/) (BSD-3, C++)
- [BDDSharp](https://github.com/ancailliau/BDDSharp) (MIT, C\#): (U Catholique Louvain)
- [LaVaBDD](http://www.ulb.ac.be/di/ssd/nmaquet/lavabdd/0.4/doc/index.html) (?, C++): Lattice-valued BDDs (ULB)
- [`wld`](http://ira.informatik.uni-freiburg.de/software/wld/) (FUSC, C++): word-level DDs (UFreiburg)
- [BDS](http://www.ecs.umass.edu/ece/labs/vlsicad/bds/bds.html) (FUSC, C): (UMass)
- [Biddy](http://biddy.meolic.com/) (GPL, C): (UMaribor)
- [list](http://bdd.hpi.uni-potsdam.de/packages.html) of BDD packages with comparisons
- [BBDD](http://lsi.epfl.ch/cms/page-102597.html) (?, ?): biconditional BDDs
- [RicBDD](https://github.com/ric2k1/RicBDD) (GPL, C++)
- [LiBDD](https://github.com/sungmaster/liBDD) (BSD, C): multi-platform BDDs package
- [BDDC](http://www-verimag.imag.fr/~raymond/tools/bddc/manual/index.html): BDD-based logical calculator
- [EHV](http://www.cs.cmu.edu/~bwolen/fmcad98/packages/ehv.html): Eindhoven BDD package

# C__#__
- [PAT.BDD](http://www.comp.nus.edu.sg/~pat/bddlib/) (?, C__#__): interface to CUDD

# Clojure
- [clj-bdd](https://github.com/dcreager/clj-bdd) (EPL, Clojure)
- [bdd](https://github.com/rhinocratic/bdd) (EPL)

# Java
- [JavaBDD](http://javabdd.sourceforge.net/) (GPL-2 or LGPL-2, Java)
- [JDD](http://javaddlib.sourceforge.net/jdd/) (zlib, Java): BDD and ZDD support, inspired by Buddy
- [JBDD](http://javaddlib.sourceforge.net/jbdd/) (zlib, Java): bindings to CUDD, Buddy
- [BeeDeeDee](https://github.com/JuliaSoft/BeeDeeDee) (GPL-2, Java): Multi-thread library
- [LightBDD](https://github.com/SigmaX/LightBDD) (?, Java): simple library
- [jSylvan](https://github.com/utwente-fmt/jsylvan) (Apache-2, C/C++/Java): JNI bindings for Sylvan
- [cpachecker](https://github.com/dbeyer/cpachecker/tree/c25691b2328ea05071c6950d02bf72b20ad81ed0/src/org/sosy_lab/cpachecker/util/predicates/bdd) (Apache-2, Java): Java bindings for Sylvan
- [JADE](http://www.informatik.uni-bremen.de/agra/eng/jade.php) (custom, Java) (UFreiburg)
- [JINC](http://jossowski.de/projects/jinc/jinc.html) (GPL-2, C++): utilizes multi-threading, has BDD, ADD, NADD, ZADD, TADD, MDD (UBonn)
- [Java applet](http://tams-www.informatik.uni-hamburg.de/applets/java-bdd/bdd-applet.html) (?, Java) (UHamburg)
- [SableJBDD](http://www.sable.mcgill.ca/~fqian/SableJBDD/) (LGPL): (McGill Univ.)
- [zdd_java](https://github.com/higotakayuki/zdd_java): educational ZDD implementation

# Javascript
- [BDD](http://fooo.fr/~vjeux/epita/bdd/) (?, Javascript)

# Julia
- [BinaryDecisionDiagrams](https://github.com/albertocasagrande/BinaryDecisionDiagrams) (MIT, Julia)

# ML
- [`muddy`](https://github.com/kfl/muddy) (MIT, ML): bindings to Buddy ([older home](http://www.itu.dk/research/muddy/)) (UCopenhagen)

# OCaml
- [`ocaml-buddy`](https://github.com/abate/ocaml-buddy) (LGPL, OCaml): bindings to Buddy ([Paris 7](http://mancoosi.org/~abate/about-me))
- [MLBDD](https://github.com/arlencox/mlbdd) (MIT, OCaml)
- [John Harrison](http://www.cl.cam.ac.uk/~jrh13/atp/OCaml/bdd.ml) (BSD-3, Ocaml)
- [Jean-Christophe Filliatre](https://www.lri.fr/~filliatr/ftp/ocaml/bdd/) (GPL-2, Ocaml)
- [`xlasat`](https://gforge.inria.fr/scm/viewvc.php/attic/xlsat/?root=sodiac) (? , Ocaml) (INRIA)

# Haskell
- [hBDD](https://github.com/peteg/hBDD) (GPL-2, Haskell): bindings to CUDD and CMU-BDD ([Australian National Univ.](http://peteg.org/))
- [hs-cudd](https://github.com/bradlarsen/hs-cudd) (BSD-3, Haskell): bindings to CUDD ([Veracode](http://bradford-larsen.net/))
- [Haskell-CUDD](https://github.com/adamwalker/haskell_cudd) (BSD-3, Haskell): bindings to CUDD ([NICTA](https://github.com/adamwalker))
- [Sylvan-Haskell](https://github.com/adamwalker/sylvan-haskell) (BSD-3, Haskell/C): bindings to Sylvan ([NICTA](https://github.com/adamwalker))
- [`termite2.bdd`](https://github.com/termite2/bdd) (?, Haskell): BDD abstraction layer (NICTA)
- [`robbed`](https://github.com/travitch/robbed) (BSD-3, Haskell): ([Galois](http://nochair.net/))
- [haskell-obdd](https://github.com/jwaldmann/haskell-obdd) (GPL-2, Haskell): ([Leipzig Univ. for Applied Sciences](http://www.imn.htwk-leipzig.de/~waldmann/))
- [`robdd`](https://github.com/slava-sh/robdd) (BSD-3, Haskell)
- [`bdd`](https://github.com/hguenther/bdd) (BSD-3, Haskell)
- [`robdd`](https://github.com/johnpmayer/robdd) (?, Haskell)

# Prolog
- [`swipl_cudd`](https://github.com/lagoonv/swipl_cudd) (?, C/Prolog): bindings to CUDD

# Lua
- [`lua-bdd`](https://github.com/silentbicycle/lua-bdd) (BSD, Lua)

# Erlang
- [seqbdd](https://github.com/shu-den/seqbdd) (BSD-like, Erlang): Sequence BDD data structure

# PHP
- [BDD](https://github.com/andreaswolf/BinaryDecisionDiagrams) (?, PHP)

# other
- [BDD papers, links](http://web.cecs.pdx.edu/~alanmi/research/dd/bddLinks.htm#BDDPackages)

# Unsorted
- [QuIDDPro](http://vlsicad.eecs.umich.edu/Quantum/qp/index.html)
- [BDS](http://ddd.fit.cvut.cz/prj/BDS/index.php?page=main)
- [MEDDLY](http://meddly.sourceforge.net/)
- [EVMDD](https://github.com/siminice/EVMDD)
- [ZBDD](http://www.aloul.net/Tools/zbddLib/)
- [`libsdd`](https://github.com/ahamez/libsdd)

# Abbreviations
- BDD = Binary Decision Diagrams
