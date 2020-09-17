List of verification and synthesis tools.
Please clone, contribute and send pull requests.
Minimal markdown knowledge needed to add links:

`- [Tool name](link url) (license, coded in language): brief description (Institution/other maintainer)`

Please list only Open Source/research tools, proprietary ones are not widely and unconditionally useful.
Conditionally (sufficiently) free tools are welcome, e.g., some closed source tools, provided they remain free for educational/research use.

Would you like to suggest a/your tool for addition, but skip cloning/pull requests, please email <jfilippidis@gmail.com>.

To the extent possible under law, the authors have waived all copyright and related or neighboring rights to this text.
You should have received a copy of the CC0 Public Domain Dedication along with this text.
If not, see <http://creativecommons.org/publicdomain/zero/1.0/>.


**Table of Contents**

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Verification with Model Checking](#verification-with-model-checking)
    - [Closed Systems (Everything controlled)](#closed-systems-everything-controlled)
        - [Enumerative](#enumerative)
        - [Symbolic](#symbolic)
    - [logic -> automata & automata tools](#logic-automata-automata-tools)
        - [LTL -> *BA](#ltl-ba)
        - [LTL -> DRA](#ltl-dra)
        - [other](#other)
    - [Term rewrite systems](#term-rewrite-systems)
    - [Open Systems](#open-systems)
        - [Synchronous Languages](#synchronous-languages)
            - [Imperative](#imperative)
            - [Declarative](#declarative)
            - [Statecharts](#statecharts)
- [Synthesis](#synthesis)
    - [Open Systems (Games: System & UnControlled Environment)](#open-systems-games-system-uncontrolled-environment)
        - [Discrete games](#discrete-games)
            - [[GR(1) games](http://dl.acm.org/citation.cfm?id=2146252) (= Generalized Reactivity 1)](#gr1-gameshttpdlacmorgcitationcfmid2146252-generalized-reactivity-1)
            - [Full LTL games](#full-ltl-games)
            - [Safety specs (controller synthesis)](#safety-specs-controller-synthesis)
            - [Parity Game solvers](#parity-game-solvers)
            - [Quantitative games](#quantitative-games)
            - [Other](#other)
        - [Hybrid games](#hybrid-games)
        - [Contracts](#contracts)
        - [Hardware](#hardware)
        - [Other](#other)
- [Timed Systems](#timed-systems)
- [Hybrid Systems](#hybrid-systems)
    - [Linear](#linear)
    - [Non-Linear](#non-linear)
    - [Stochastic](#stochastic)
- [Theorem Provers](#theorem-provers)
    - [Theorem provers for modal logics](#theorem-provers-for-modal-logics)
    - [QBF](#qbf)
    - [SAT](#sat)
        - [CDCL](#cdcl)
        - [Stochastic local search](#stochastic-local-search)
        - [Parallel](#parallel)
        - [Unsorted](#unsorted)
    - [SMT](#smt)
    - [Other solvers](#other-solvers)
    - [Logic programming](#logic-programming)
- [Software Synthesis](#software-synthesis)
- [Runtime Verification](#runtime-verification)
- [Yet un-categorized](#yet-un-categorized)
- [TypeSetting](#typesetting)
- [Other tool lists](#other-tool-lists)
- [databases and benchmarks](#databases-and-benchmarks)
- [(non-common) abbreviations](#non-common-abbreviations)

<!-- /TOC -->



# Verification with Model Checking

## Closed Systems (Everything controlled)

### Enumerative
- [SPIN](http://spinroot.com/spin/whatispin.html) (BSD-3, [C](https://github.com/nimble-code/Spin)): LTL model checking for closed systems in Promela ([JPL/Caltech](http://lars-lab.jpl.nasa.gov/), Bell Labs)
    * [modex](http://spinroot.com/modex/) (FUSC, [C](https://github.com/nimble-code/Modex)): C -> Promela: model extractor ([JPL/Caltech](http://lars-lab.jpl.nasa.gov/), Bell Labs)
    * [`spin`](https://packages.debian.org/buster/spin): Debian Linux package, `apt install spin`
    * [spinja](http://code.google.com/p/spinja/) (Apache, Java): Promela model checker (Univ. Twente, TNO)
    * [HSF-SPIN](http://www.albertolluch.com/research/tools): SPIN directed model checking extension (IMT Lucca)
    * [Promela Vim Syntax](https://github.com/vim-scripts/promela.vim) (?, VimL): highlighting plugin
    * [Promela Vim Indent](https://github.com/vim-scripts/promela) (?, VimL)
    * [Promela Emacs major mode](https://github.com/emacsmirror/promela-mode) (?, Emacs LISP)
    * [Promela -> NuSMV](https://code.google.com/p/s2n/) (?, C): translator (Peking Univ.)
    * [Promela -> Timed automata with discrete data](http://verics.ipipan.waw.pl/promela): translator, part of Verics
    * [Promela -> C](http://www.ida.liu.se/~kejia/c2promela/) (OCaml): translator (Uppsala Univ.)
    * [Promela -> C](http://www.mathematik.uni-stuttgart.de/~floeff/publications/96-enstparis-s2-report.pdf): translator (Univ. Stuttgart)
    * [Promela -> Java](http://members.tele2.nl/edwin.v/compiler.html) (?, Java): translator ([TU Delft](http://members.tele2.nl/edwin.v/index.html))
    * [LLVM -> Promela](https://github.com/roselone/pmGen) (C++, MIT): LLVM-to-Promela Compiler
    * [jSpin](http://code.google.com/P/Cjspin/) (GPL-2, Java): GUI for SPIN and Erigone
    * [Erigone](http://code.google.com/p/erigone/) (GPL-2, Ada): partial SPIN re-implementation for educational purposes
    * [EpiSpin](http://epispin.ewi.tudelft.nl/): Eclipse plug-in for editing & verifying Promela using Spin ([TU Delft](http://swerl.tudelft.nl/twiki/pub/Main/PastAndCurrentMScProjects/thesis-bob-de-vos.pdf))
    * [`promela` parser](https://github.com/johnyf/promela) (BSD-3, Python): parser for Promela using [PLY](http://www.dabeaz.com/ply/ply.html) (Python `lex`-`yacc`) ([Caltech](http://www.cds.caltech.edu/~ifilippi/))
    * [`language-promela`](https://github.com/ubinix-warun/language-promela) (MIT, CoffeeScript): Promela support in Atom
    * [Eclipse Pug-In for SPIN](http://matrix.uni-mb.si/en/science/tools/eclipse-plug-in-for-spin//) (?): (Univ. Maribor, TU Braunschweigin)
    * [st2msc](http://matrix.uni-mb.si/en/science/tools/st2msc-tool/) (?, Java): SPIN trail -> Message Sequence Chart (Univ. Maribor)
    * [Real-Time SPIN](http://www-verimag.imag.fr/~tripakis/rtspin.html): quantitative dense time SPIN extension using Real-Time Promela ([VERIMAG/CNRS](http://www-verimag.imag.fr/~tripakis/index.html))
    * [nano-Promela](https://bitbucket.org/simonhj/nano-promela): tools for nano-Promela language
    * [v-Promela](http://tele.informatik.uni-freiburg.de/leue/visual.html#isorc99): visual Promela (Albert-Ludwigs-Univ. Freiburg)
    * [promela-metamodel](https://code.google.com/p/promela-metamodel/): used to generate Promela from BPEL
    * [Promela library](https://forge.ocamlcore.org/projects/promela/) (BSD-3, OCaml): types for Promela expressions, statements, procs and models as OCaml datastructures, with export to Promela for model checking with SPIN (TU Munchen)
    * [LWAASpin](http://www.pst.ifi.lmu.de/projekte/lwaaspin/) (SPIN's license): SPIN modified to use linear weak alternating automata instead of Buchi automata (Univ. Munchen)
    * [Hugo/RT](http://www.pst.informatik.uni-muenchen.de/projekte/hugo/) (? src by email): XMI | ArgoUML | UTE -> Promela | UPPAAL | KIV | Java | SystemC | Smile machines | UTE model | dot (state machines | interactions) and SPIN | UPPAAL trail -> UML run: UML model translator for model checking, theorem proving, code generation (Univ. Munchen, LORIA/INRIA Nancy)
    * [SCTranslator](https://github.com/Alagert/SCTranslator) (?, XSL): UML XMI2 -> Promela (Saint-Petersburg State Polytechnic University)
    * [Pi2Promela](http://lcs.ios.ac.cn/~wp/pi2pro_manual.html) (?, C/Java): compiler from pi-calculus models to Promela, includes GUI ([Chinese Acad. Sciences](http://lcs.ios.ac.cn/~wp/))
    * [pspin](https://github.com/tw33dl3dee/pspin) (?, Python/C): Parallel PROMELA model checker
    * [prob-Promela](https://github.com/hhu-stups/prob-promela): Promela Compiler / Interpreter for ProB (Dusseldorf Univ.)
    * [Promela parser/pretty printer](https://github.com/hguenther/language-promela) (?, Haskell)
    * [sudoku-Promela](https://github.com/davidfischer-ch/sudoku-promela) (EUPL, Shell): mini-project about generating Sudoku grids in Promela
    * [VMSSG](http://www.pst.ifi.lmu.de/~hammer/statespaces/): Model checker state space visualization (Ludwig-Maximilians Univ. Munchen)
    * [promela-metamodel](http://code.google.com/p/promela-metamodel/) (GPL-3)
    * [3Spin](http://3spin.peterd.org/)
    * [POR](http://www.montefiore.ulg.ac.be/services/verif/po-pack.html) (?, C): partial-order reduction package for SPIN ([Univ. de Liege](http://www.montefiore.ulg.ac.be/services/verif/Welcome-en.html))
    * [ARINC tester](http://www.gisum.uma.es/tools/arinctester/) (?, Java): GUI for SPIN to verify application that contain API calls compliant to ARINC 653 (UMalaga)
    * [SpinRCP](http://lms.uni-mb.si/spinrcp/index.html) (?, Java) An Eclipse-based IDE for Spin. (Univ. of Maribor)
- [TLA+](http://lamport.azurewebsites.net/tla/tla.html): The Temporal Logic of Actions for specifying systems ([Microsoft Research](http://lamport.org))
    * [The TLA+ Video Course](http://lamport.azurewebsites.net/video/videos.html): Lectures about writing specifications, by Leslie Lamport
    * [PlusCal](http://lamport.azurewebsites.net/tla/pluscal.html): An algorithm language with a translator to TLA+
    * [TLA+ Tools](http://lamport.azurewebsites.net/tla/tools.html), (MIT, [Java](https://github.com/tlaplus/tlaplus)): Tools for working with TLA+ specifications:
        + [TLC](http://lamport.azurewebsites.net/tla/tlc.html) (MIT, Java): Model checker for TLA+ specifications
        + [SANY](http://lamport.azurewebsites.net/tla/sany.html) (MIT, Java): Parser and semantic analyzer for TLA+ ([ANTLR](http://www.antlr.org/)-based)
        + [TLATeX](http://lamport.azurewebsites.net/tla/tlatex.html) (MIT, Java): Program for typesetting TLA+ specs
        + [The TLA Toolbox](http://lamport.azurewebsites.net/tla/toolbox.html) (MIT, Java): An IDE for the TLA+ tools (Eclipse-based), includes TLC, SANY, TLATeX, and the PlusCal translator
        + [TLAPS](http://tla.msr-inria.inria.fr/tlaps/content/Home.html): See automated theorem provers section.
        + Tools for working with TLA+ proofs: See automated theorem provers section.
    * [`tla_tools`](https://github.com/joewilliams/tla_tools) (MIT, Shell): Helper tools for using TLA+ (wrappers etc.) ([GitHub](https://github.com/joewilliams))
    * [tla related tools](https://github.com/hhu-stups) (Dusseldorf Univ.)
    * [TEM](http://ls4-www.cs.tu-dortmund.de/RVS/P-TLA/TEM/tem.html) (GPL, Emacs): TLA+ major mode for GNU EMACS 19 (TU Dortmund)
    * [language-tla-pluscal](https://github.com/wysiib/language-tla-pluscal) (MIT, CoffeeScript): TLA + and PlusCal Language Support in Atom ([Heinrich-Heine-Univ.](https://krin.gs/))
    * [TLAGrammar](https://github.com/agentultra/TLAGrammar) (MIT): Textmate-compatible grammar for TLA+ (used to highlight TLA+ on github)
    * [`vim-scripts/TLA`](https://github.com/vim-scripts/TLA) (GPL, VimL): TLA+ plugin for Gvim
    * [`vim-scripts/tla.vim`](https://github.com/vim-scripts/tla.vim) (?, VimL): Vim syntax highlighting for TLA+
    * [`tla.vim`](https://github.com/hwayne/tla.vim) (MIT, VimL): Vim plugin for TLA+ and PlusCal
    * [eTLA](https://sourceforge.net/projects/etla/) (EPL): TLA+ plugin for Eclipse
    * [textadept-TLA-](https://github.com/Hackerpilot/textadept-TLA-) (MIT, Lua): TLA+ and PlusCal syntax highlighting for Textadept
    * [`tla-parser-s`](https://github.com/jarjuk/tla-parser-s) (MIT, Ruby): TLA+ parser (Helsinki)
    * TLA+ examples:
        - [TLA Tools examples](https://github.com/tlaplus/Examples)
        - [MultiPaxos](https://github.com/nano-o/MultiPaxos)
        - [Egalitarian Paxos](https://github.com/efficient/epaxos) (CMU, Intel Labs)
        - [Leaderless Byzantine Paxos](https://bitbucket.org/ngunatillaka/leaderless-byzantine-paxos) (UNSW)
        - [Raft consensus algorithm](https://github.com/ongardie/raft.tla)
        - [TLA-Library](https://github.com/nano-o/TLA-Library)
        - [MongoDB](https://github.com/visualzhou/mongo-repl-tla): simplified part of MongoDB replication system (MongoDB)
        - [Convergence locking](https://github.com/ryansb/heat-tla-model)
    * [tTLA+ Browser](http://ls4-www.cs.tu-dortmund.de/RVS/P-TLA/TBR/tbr.html) (FUSC, C): old project about a TLA+ IDE (TU Dortmund)
    * [Tools for TLA](http://ls4-www.cs.tu-dortmund.de/RVS/P-TLA/welcome.html): old TLA+-related project (TU Dortmund)
    * [TLA within ProB](https://www3.hhu.de/stups/prob/index.php/TLA): (Heinrich Heine Univ. Düsseldorf)
        * [`tla2b`](https://github.com/hhu-stups/tla2b) (EPL, Java)
        * [`tla2bAST`](https://github.com/hhu-stups/tla2bAST) (EPL, Java)
        * [`tlc4b`](https://github.com/hhu-stups/tlc4b) (EPL, Java)
- [LTSmin](http://fmt.cs.utwente.nl/tools/ltsmin/) (BSD-3): model checking, LTS minimization, interface to other tools (Univ. Twente)
- [MoonWalker](http://fmt.cs.utwente.nl/tools/moonwalker/) (Apache-2, C#): model check CIL bytecode programs ([Mono .NET](http://www.mono-project.com/Main_Page) platform apps), [MoonWalker src](http://code.google.com/p/moonwalker/)(Univ. Twente)
- [DIVINE-2](http://divine.fi.muni.cz/) (BSD-3): Parallel LTL model checking, [DIVINE](http://divine.fi.muni.cz/darcs/mainline/gui/help/divine/divine-cluster.html) (Masaryk Univ.)
- [PRISM](http://www.prismmodelchecker.org/) (GPLv2, [Java/C](https://github.com/prismmodelchecker/)): Probabilistic Model Checker: discrete/continuous-time Markov chains, timed automata, etc. (Univ. Birmingham, Univ. Oxford)
    * [PRISM tools](http://www.prismmodelchecker.org/other-tools.php)
    * [prism-games](http://www.prismmodelchecker.org/games/) (GPLv2, [Java/C](https://github.com/prismmodelchecker/prism-games)): an extension of PRISM which supports stochastic games
- [STORM](http://www.stormchecker.org) (GPL-3, [C++](https://github.com/moves-rwth/storm)): Probabilistic model checker: Markov chains, MDPs, Markov automata, SMPT, (MI)LP, LP, Bellman, games, parameter synthesis, discrete-time MDPs
    * [`stormpy`](https://github.com/moves-rwth/stormpy): Python interface
- [SPOT](http://spot.lip6.fr/wiki/) (GPL, C++/Python): object-oriented model checking library using TGBA
- [JPF](http://babelfish.arc.nasa.gov/trac/jpf) ([NOSA-1.3](http://javapathfinder.sourceforge.net/NOSA-1.3-JPF.txt)): Java Pathfinder: Java model checking & extensions (NASA Ames)
    * [JPL-nhandler](https://bitbucket.org/nastaran/jpf-nhandler) (GPL-3, Java): JPF extension to delegate execution of SUT methods to host JVM ([York Univ.](http://www.nastaran.ca/))
- [HELENA](http://sourceforge.net/projects/helena-mc/) (GPL-2): high-level Petri nets (Paris 13 Univ.)
- [StEAM](http://steam.cs.uni-dortmund.de/) (C++ ?): C++ model checker (deadlocks, segmentation faults, out of range variables and non-terminating loops) (LS5 Univ. Dortmund)
- [Tulip](http://tulip.lenhardt.co.uk/): LTL model checker of interval Markov chains (recursive also) (Univ. Oxford)
- [PROD](http://www.tcs.hut.fi/Software/prod/) (GPL): efficient reachability analysis (Helsinki Univ. Tech.)
- [KBDD](http://www.cs.rice.edu/CS/Verification/Software/software.html): BDD-based satisfiability solver for modal logic K
- [neco](https://code.google.com/p/neco-net-compiler/) (LGPL, Python/Cython): Petri Net compiler & LTL model checker (Univ. d'Evry-Val d'Essonne, Univ. Evry)
- [PEP](http://sourceforge.net/projects/peptool/) (GPL-2): modelling and verification framework for parallel systems, interfaces to SPIN, SMV, INA, FC2Tools (SDL, Petri nets)
- [cunf](http://code.google.com/p/cunf/) (GPL-3): Toolset for unfolding-based verification of Petri nets extended with read arcs ([ENS Cachan](http://www.lsv.ens-cachan.fr/~rodriguez/))
- [daj](http://code.google.com/p/daj/) (GPL-2, Java): interactive, visual aid for studying execution of distributed algorithms
- [FC2Tools & Autograph](http://www-sop.inria.fr/meije/verification/): implementation of process algebra theory, verification by compositional reductions and abstraction, explicit/implicit BDD, FC2 file exchange format (INRIA, Ecole des Mines/CMA)
- [ESBMC](http://users.ecs.soton.ac.uk/lcc08r/esbmc/) (BSD-3): context-bounded model checker for embedded C/C++ software based on Satisfiability Modulo Theories (SMT) solver (Univ. Southampton)
- [Murphi](http://www.cs.utah.edu/formal_verification/Murphi/), [original Murphi](http://verify.stanford.edu/dill/murphi.html) (BSD-like, C++): enumerative, own input language (Unity style: guard -> action), e.g. used by Microprocessor industry to verify cache coherence protocols (Univ. Utah, Stanford)
    * [Eddy Murphi](http://www.cs.utah.edu/formal_verification/EddyMurphi/): parallel version of Murphi (Univ. Utah)
    * [CMurphy](http://mclab.di.uniroma1.it/site/index.php/software/18-cmurphi) (Univ. Roma)
    * [CMurphi](http://www.di.univaq.it/gdellape/lamoka/page.php?pid=246&lid=en) (L'Aquila Univ.)
    * [PReach](https://bitbucket.org/jderick/preach/wiki/Home) (BSD, Erlang): Distributed Explicit State Model Checker based on Erlang and Murphi (Univ. British Columbia, Intel)
    * [MPI Murphi port](http://www.cs.utah.edu/formal_verification/software/murphi/murphi.hemanth/index.only_hemanth.html) (Univ. Utah)
- [APMC](http://sylvain.berbiqui.org/apmc) (FUSC, C/Java): approximate distributed for fully probabilistic systems, PCTL, PLTL (Univ. de Caen Basse-Normandie)
- [Vaucanson](http://www.lrde.epita.fr/cgi-bin/twiki/view/Vaucanson/) (GNU, C++): finite state machine manipulation platform, lib of tools on top (EPITA)
- [Genealogy](http://spot.lip6.fr/wiki/EmptinessCheckAlgorithms) of Emptiness-Checking Algorithms ([EPITA](http://www.lrde.epita.fr/~adl/))
- [NIPS](http://www.foldr.org/~michaelw/projects/gitweb?p=nips-vm.git;a=summary) (GNU, C/Perl): A virtual machine for state space generation (RWTH Aachen)
- [VMSSG Statespace Converter](http://www.pst.informatik.uni-muenchen.de/~hammer/statespaces/manual.html) (GPL, Java): process, analyze, display statespace graphs produced by modified VMSSG virtual machine, [state space gallery](http://www.pst.ifi.lmu.de/~hammer/statespaces/index.html), ([Univ. Munchen](http://www.pst.ifi.lmu.de/Personen/ehemalige/hammer/hammer/view))
- [Synet](http://www.irisa.fr/s4/tools/synet/) (OCaml): Synthesizer of distributable bounded Petri nets from Finite Automata ([INRIA/IRISA](http://www.irisa.fr/prive/Benoit.Caillaud/Benoit_Caillauds_Professional_homepage/Welcome.html))
- [Motion Grammar Kit](https://github.com/golems/motion-grammar-kit) (BSD-2, Common Lisp/C): Automata manipulation, supervisory control, C code generation (Georgia Tech.)
- [PAT](http://en.wikipedia.org/wiki/PAT_%28model_checker%29) (?, C#): GUI, model editor, simulator, POR, symmetry reduction (Nat. UNiv. Singapore)
- [NorMC](https://github.com/pkazmierczak/NorMC) (BSD-3, Haskell): Norm compliance temporal logic model checker (Univ. Bergen)
- [Copper](http://www.sei.cmu.edu/predictability/tools/copper/index.cfm) (FUSC, ?): MC for concurrent message-passing C programs (CMU)
- [Magic](http://www.cs.cmu.edu/~chaki/magic/) (?): Check C language conformance between component specifications and their implementations using counterexample guided abstraction refinement, concurrent and compositional (CMU, Univ. Wisconsin, Univ. Oxford, TU Vienna, Univ. Lugano)
- [Bogor](http://bogor.projects.cis.ksu.edu/manual/)
- [BLAST](http://mtc.epfl.ch/software-tools/blast/index-epfl.php) (Apache, OCaml/C): MC for C programs using counterexample-driven automatic abstraction refinement (UC Berkeley, EPFL, UCSD, UCLA, Simon Fraser Univ.)
- [CBMC](http://www.cs.cmu.edu/~modelcheck/cbmc/) (BSD-4): Bounded MC for ANSI-C | C++ | SystemC | Scoot, uses Boolector | MathSAT | Z3
    * [Eclipse plugin](http://www.cprover.org/eclipse-plugin/)
    * [Visual Studio plugin](http://www.cprover.org/visual-studio/)
- [EBMC](http://www.cprover.org/ebmc/) (BSD-5): Bounded Model Checker for hardware designs, inputs: Netlists/ISCAS89 | Verilog | SMV, exports: DIMACS CNF | SMT-LIB (CMU, ETHZ, Oxford Univ.)
- [Scoot](http://www.cprover.org/scoot/) (?): Static analysis of SystemC, model extraction to pass to SatAbs | CBMC, C++ re-synthesis (ETH)
- [VCEGAR](http://www.cs.cmu.edu/~modelcheck/vcegar/) (?): Check safety (assertions) of Verilog, using word level predicate abstraction and refinement (CMU, Oxford Univ.)
- [GMC](http://d3s.mff.cuni.cz/~sery/gmc/index.html) (LGPL, C/C++): MC for C/C++ taking GIMPLE as input (Charles Univ. Prague)
- [AIR](http://www.contrib.andrew.cmu.edu/~schaki/publications/NFM-2009.html) (?): Safety MC of Assembly using predicate abstraction and counterexample guided abstraction refinement ([CMU](http://www.contrib.andrew.cmu.edu/~schaki/index.html))
- [FShell](http://forsyte.at/software/fshell/) (Apache): Interactive & Scripting testing environment for C programs, frontend for software model checkers, dispatches queries to analysis tools (TU Wien)
- [CPA/Tiger](http://forsyte.at/software/cpatiger/) (?): Predicate-abstraction based test input generator for C programs, uses CPAchecker (TU Wien)
- [CPAchecker](http://cpachecker.sosy-lab.org/) (Apache): Configurable software verification (Univ. Passau)
- [crest](https://code.google.com/p/crest/) (BSD-3): Automatic test generation tool for C, inserts instrumentation code and solves the generated symbolic constraints using Yices (UC Berkeley)
    * [ConCREST](http://forsyte.at/software/concrest/) (?): Concolic testing tool for multi-threaded C programs (Univ. Toronto, TU Wien)
- [ByMC](http://forsyte.at/software/bymc/) (?, OCaml): Byzantine MC for parameterized model checking of (threshold-guarded) fault-tolerant distributed algorithms in Promela extension using SPIN, Yices (TU Wien)
- [iLTL](http://osl.cs.illinois.edu/software/iltl/index.html) (BSD): MC for iLTL, which specifies temporal changes of expected rewards of a Markov process ([UIUC](https://sites.google.com/site/youngminkwon/))
- [Copilot](http://leepike.github.io/Copilot/) (BSD-3, Haskell): A (Haskell DSL) stream language for generating hard real-time C code (NASA, galois Inc., National Inst. Aerospace, Ecole Normale Superieure, TU Ilmenau, Univ. Copenhagen)
- [mCRL2](http://www.mcrl2.org/release/user_manual/index.html) (Boost Software License, C++): Formal specification language with an associated toolset for modelling, validation and verification of concurrent systems and protocols: linearisation, simulation, state-space exploration, visualization and tools to optimise and analyse specifications, μ-calculus (TU Eindhoven, LaQuSo, CWI, Univ. Twente)
- [Mobility Workbench](http://www.it.uu.se/research/group/mobility/mwb) (?, SML): π-calculus MC for mobile concurrent systems (Uppsala Univ.)
- [MMC](http://www.cs.sunysb.edu/~lmc/mmc/) (?, ?): π-calculus and alternation-free μ-calculus Local MC, implemented using the XSB tabled logic programming system (Stony Brook Univ.)
- [XMC](http://www.cs.sunysb.edu/~lmc/) (?, ?): Local MC for processes specified in XL, a version of value-passing CCS, and the alternation-free modal μ-calculus, implemented using the XSB tabled logic programming system (Stony Brook Univ.)
- [MMCsp](http://lcs.ios.ac.cn/~wp/mmc_sp_manual.html) (?, C/Java): Compiler from simple probabilistic π-calculus to PRISM models, built on XSB (Ecole Polytechnique, Oxford, INRIA)
- [ASTG](http://lcs.ios.ac.cn/~wp/astg_manual.html) (?, OCaml/C): TLCE-based symbolic test generator (Chinese Acad. Sciences)
- [LMNtal, LaViT](http://www.ueda.info.waseda.ac.jp/lmntal/) (BSD, C/C++/Java): MC and graphical tools LMNTal language based on hierarchical graph rewriting (Waseda Univ.)
- [Finite Automata Model Checker](https://bitbucket.org/jwright/finite-automata-model-checker) (CCAS-3, C++)
- [v-n](http://code.google.com/p/v-n/) (GPL-2, Java): NDFA visualization and (random or guided) simulation, find and display accepting computations ([Weizmann Inst. Sc.](https://en.wikipedia.org/wiki/Mordechai_Ben-Ari))
- [py-powerset-construction](http://code.google.com/p/py-powerset-construction/) (GPL-3, Python): convert NFA-\lambda to DFA, using dot as input
- [Zing](http://research.microsoft.com/en-us/projects/zing/) (Non-com, C#): State exploration of concurrent software systems (Microsoft research)
- [SeaHorn] (https://github.com/seahorn/seahorn) (BSD, C): an LLVM based verification framework
- [SCRAM](https://github.com/rakhimov/scram)(GPL-3, C++/Python): Probabilistic risk analysis (static fault trees, common cause failure models, Monte Carlo) with input from and output to Open-PSA model exchange format files
- [RISCAL](https://www.risc.jku.at/research/formal/software/RISCAL/) (GPL-3, Java): Specification language and software system for describing mathematical algorithms, and validating their correctness by execution/evaluation ([JKU/RISC](https://www.risc.jku.at/home/schreine))


### Symbolic
- [Apalache](https://github.com/konnov/apalache) (Apache-2, Scala): symbolic model checker for TLA+
- [SMV](http://www.cs.cmu.edu/~modelcheck/smv.html) (?): CTL symbolic model checker (CMU)
    * [Cadence SMV](http://www.kenmcmil.com/smv.html) (FUSC): CMU SMV extension: backward compatible more expressive mode description language, synthesizable VERILOG, compositional verification, CTL | LTL | FSA | embedded assertions, GUI (Cadence)
- [NuSMV](http://nusmv.fbk.eu/) (LGPL): Symbolic model checking (FBK, CMU, Univ. Genoa, Univ. Trento)
    * [PyNuSMV](http://lvl.info.ucl.ac.be/Tools/PyNuSMV) (LGPL-2, Python): python interface to NuSMV ([UCLouvain](http://lvl.info.ucl.ac.be/))
    * [SMView](https://github.com/ArnoVanLumig/smview) (BSD, JavaScript/Python): web interface to NuSMV (TU Eindhoven)
    * [gNuSMV](http://nusmv.fbk.eu/gnusmv/) (LGPL, ?): GUI for NuSMV v2 (FBK)
    * [nusmv-tools](https://code.google.com/a/eclipselabs.org/p/nusmv-tools/): two metamodels based on Eclipse modeling framework, Eclipse editor, model analyzer, Java API to NuSMV
    * [nuseen](https://code.google.com/a/eclipselabs.org/p/nuseen/): Eclipse-based environment for NuSMV
- [nuXmv](https://es-static.fbk.eu/tools/nuxmv/index.php): extends NuSMV using state-of-the-art SAT-based algorithms and MathSAT5 (Fondazione Bruno Kessler)
- [Mocha](http://mtc.epfl.ch/software-tools/mocha/), also [here](http://www.cis.upenn.edu/~mocha/) (BSD, Java | C/Tcl/Tk): Interactive environment for system specification (reactive modules language), execution (randomized, guided, mixed), requirement specification (Alternating Temporal Logic, superset of CTL), ATL MC, implementation verification (EPFL, UC Berkeley, UPenn, SUNYSB)
- [jStar](http://www.jstarverifier.org/) (BSD-3, OCaml): (Queen Mary Univ. London, Cambridge Univ., ETH)
- [coreStar](https://github.com/seplogic/corestar) (BSD-3, OCaml): symbolic execution engine for analysis and verification with separation logic (Queen Mary Univ. London, Univ. Cambridge)
- [JSCert JuS](http://jscert.org/index.html): Certified JavaScript (Imperial College, INRIA)
    * [jabstr](https://github.com/MatkoBotincan/jabstr) (LGPL, Ocaml): jStar plugin for numerical abstractions
- [LStar](https://bitbucket.org/jvillard/lstar/wiki/Home) (BSD-3, OCaml): automatic prover for programs written in bitcode using separation logic (UCL)
- [VIS](http://vlsi.colorado.edu/~vis/): logic circuit simulation, circuit verification, fair CTL model checking, logic synthesis via hierarchy restructuring [UC Berkeley, Univ. Colorado at Boulder, Univ. Texas at Austin]
- [VerICS](http://verics.ipipan.waw.pl/start) (FUSC, Java): SAT verification of timed & multi-agent systems modeled by networks of communicating automata (Polish Academy of Sciences)
- [Augur 2](http://www.ti.inf.uni-due.de/research/tools/augur2/) (GPL-2, C++): verification of systems described by (attributed) graph transformations using approximated unfoldings ([Univ. Duisburg-Essen](http://www.ti.inf.uni-due.de/people/koenig/))
- [Mercury](http://rodrigotaclasaad.drupalgardens.com/content/mercury): Parallel Local Sub-CTL Model Checking [LAAS-CNRS]
- [Boogie](http://research.microsoft.com/en-us/projects/boogie/) ([Ms-PL](http://boogie.codeplex.com/license), F#/C#): Intermediate verification language, intended as a layer on which to build program verifiers for other languages (Microsoft Research)
    * [SymDiff](http://research.microsoft.com/en-us/projects/symdiff/default.aspx): Language-independent differential program analysis (C, Boogie front-ends available) (Microsoft Research)
- [VCC](http://research.microsoft.com/en-us/projects/vcc/default.aspx) ([FUSC](http://vcc.codeplex.com/license), F#/C#/C/Perl): annotated concurrent C programs (Microsoft Research)
- [HAVOC](http://research.microsoft.com/en-us/projects/havoc/default.aspx) (?): for C in the presence of pointer manipulations, unsafe casts and dynamic memory allocation (Microsoft Research)
- [Dafny](http://dafny.codeplex.com/) ([Ms-PL](http://dafny.codeplex.com/license), C#): imperative object-based language with built-in specification constructs and static program verifier for functional correctness ([Microsoft Research](http://research.microsoft.com/en-us/um/people/leino/))
    * [sublime Dafny](https://github.com/erggo/sublime-dafny): Sublime Text 2 plugin for Dafny. Provides verifing and syntax highlighting ([Imperial College London](http://tomas.virgl.net/))
- [Spec\#](http://specsharp.codeplex.com/) ([FUSC](http://specsharp.codeplex.com/license), C#): Object-oriented .NET programming language with design-by-contract features for method pre-/postconditions & object invariants, non-null type system (Microsoft Research)
- [Whiley](https://github.com/DavePearce/Whiley) (BSD-3, Java/C/): Object-oriented and functional programming language with static checking, including: divide-by-zero, array out-of-bounds and null dereference errors ([Victoria Univ. of Wellington](http://homepages.ecs.vuw.ac.nz/~djp/))
- [Why3](http://why3.lri.fr/) (GPl-2, OCaml): platform for deductive program verification in WhyML, uses external theorem provers, extracts OCaml from WhyML ([INRIA, Univ. Paris Sud, CNRS, LRI](http://toccata.lri.fr/))
    * [EasyCrypt](http://software.imdea.org/projects/certicrypt/) (?, OCaml): toolset for reasoning about relational properties of probabilistic computations with adversarial code (IMDEA Software Institute, Microsoft Research)
    * [GNATprove](http://www.open-do.org/projects/hi-lite/gnatprove/) (GPL): Ada 2012 prover
    * [Krakatoa](http://krakatoa.lri.fr/): Java verification
    * [BWare](http://bware.lri.fr/index.php/BWare_project): discharging proof obligations generated by Atelier B using multiple provers
    * [MiniMaple](https://www.risc.jku.at/people/mtkhan/dk10/software.html) (GPL-3, Java): Software for formal specification and verification of Maple programs by translation to Why3ML ([JKU](https://www.risc.jku.at/home/mtkhan))
- [KeY](http://en.wikipedia.org/wiki/KeY) (GPL, Java): Formal verifier of HML | OCL specs for JAVA, via dynamic logic thms (Karlsruhe Inst. Tech., TU Darmstadt, Chalmers Univ. Tech.)
    * [KeY-Hoare](http://www.key-project.org/download/hoare/) (GPL, Java): Hoare calculus with updates, extension of KeY (KIT, TUD, Chalmers)
    * [KeYmaera](http://symbolaris.com/info/KeYmaera.html) (GPL, Java): Theorem prover for hybrid systems: deductive, real algebraic, and computer algebraic prover technologies ([CMU](http://symbolaris.com/andre.html))
    * [KeYmaeraD](http://symbolaris.com/info/KeYmaeraD.html), its [github](https://github.com/keymaerad/KeYmaeraD) (BSD-3, Scala): Distributed theorem prover for distributed hybrid systems using Quantified differential dynamic logic (QdL) ([CMU](http://symbolaris.com/andre.html))
    * [SPHINX](http://www.cs.cmu.edu/afs/cs/Web/People/smitsch/tools.html) (?): Eclipse plugin for textual & graphical modeling editors to define cyber-physical system structure, discrete/continuous dynamics ([CMU](http://www.cs.cmu.edu/afs/cs/Web/People/smitsch/index.html))
- [j-algo](http://j-algo.binaervarianz.de/index.php?language=en) (GPL, Java): Algorithm visualization tool (TU Dresden)
- [Verus](http://www.cs.cmu.edu/~modelcheck/verus.html) (?): Language for real-time systems, CTL symbolic MC, compilation into state-transition graph (CMU)
- [UCLID](http://www.cs.cmu.edu/~uclid/) (BSD-like, Moscow ML): Model & verify nfinite-state systems with variables of integer, Boolean, function, and array types, term-level bounded model checking, correspondence checking, deductive verification, and predicate abstraction-based verification, and stand-alone decision procedure for the theories of uninterpreted functions and equality, integer linear arithmetic, and arrays (CMU, UC Berkeley)
- [CBMC-GC](http://forsyte.at/software/cbmc-gc/) (?): C compiler in the context of Secure Two-party Computation (STC) (TU Wien, TU Darmstadt, CASED, CrypTool Project)
- [Chic](http://en.wikipedia.org/wiki/CHIC_%28electronics%29) (BSD, Java): Modular verifier for behavioral compatibility checking of hardware and software systems (UC Berkeley)
- [BLAST](http://mtc.epfl.ch/software-tools/blast/index-epfl.php) (Apache, OCaml): software MC for C using Lazy abstraction (UC Berkeley, EPFL)
- [CRefine](http://www.cs.york.ac.uk/circus/tools/refinement.php) (?, Java): Verifies `Circus` specs purely by applying various well-proved refinement laws, requires veriT (Univ. York)
- [UTP and Cirus Theories in ProofPower-Z](http://www.cs.york.ac.uk/circus/tools/utp.php) (?, ?): embedding the theories (relations, designs, reactive processes) of UTP in the theorem prover ProofPower-Z, formal proofs can be mechanically constructed (Univ. York)
- [Circus Type Checker](http://www.cs.york.ac.uk/circus/tools/type.php) (? , Java): Syntax type checker for Circus specifications (Univ. York, UFPCI)
- [JCircus](http://www.cs.york.ac.uk/circus/tools/jcsp.php) (?, Java): Automatically translate Circus programs into Java, for the purpose of animation and simulation (Univ. York)
- [ClawCircus](http://www.cs.york.ac.uk/circus/tools/control.php) (?, Java): Java-based tools primarily for generating Circus models from Simulink (Univ. York)
- [Circus Parser](http://sourceforge.net/projects/czt/) (GPL-2, Java): Included in Community Z tools (Univ. York)
- [Rodin](http://www.event-b.org/) (EPL, Eclipse): Eclipse-based platform for refinement and mathematical proof of Event-B (Univ. Southampton)
- [CheckFence](http://checkfence.sourceforge.net/) (BSD, OCaml): SAT-based analysis of C code implementing concurrent data types (UPenn)
- [Daikon](http://en.wikipedia.org/wiki/Daikon_%28system%29) (MIT, Java): Dynamic invariant detection for C/C++, Eiffel, IOA, Perl (MIT)
- [Tip](https://github.com/niklasso/tip) (?, C++/C): (Temporal Induction Prover) SAT based model checker ([Chalmers Univ.](http://minisat.se/Authors.html))
- [alloy](http://alloy.mit.edu/alloy/): Language inspired by Z spec language and Tarski's relational calculus for implicitly describing structures and tool for exploring and generating counterexamples (MIT)
- [IVy](http://microsoft.github.io/ivy/) (MIT, [Python](https://github.com/Microsoft/ivy)): A tool for specifying, modeling, implementing and verifying protocols (MSR, Tel Aviv Univ., UCB)
- [PyCSP](http://code.google.com/p/pycsp/) (MIT, Python): communicating sequential processes in Python (Aarhus Univ.)
- [FDR2](https://en.wikipedia.org/wiki/FDR2): Refinement checker for communicating sequential processes (Oxford Univ.)
- [KRATOS](https://es-static.fbk.eu/tools/kratos/): MC for sequential and cooperative multi-threaded C programs, verifying safety properties (Bruno Kessler Found.)
- [Mr. Waffles](http://mrwaffles.gforge.inria.fr/index.html) (GPL-2, Python): bare-bones CTL MC (Nancy Univ., LHS/LORIA, ESEC R&D)
- [Peirce-Logic](https://github.com/CurryBoy/Peirce-Logic) (BSD-3, JS): Existential Graph proof system ([RPI](http://www.dimit.me/))
- [VSE](http://www.dfki.de/vse/projects/vse.html): verification support environment (DFKI, IST, Univ. Ulm, DASA)
    * [VSE II](http://www.dfki.de/vse/projects/vse-short.html): Enhancing VSE with concurrency, structural deduction, and an integrated theorem prover
- [Leon](http://lara.epfl.ch/w/leon) (Scala): automated synthesis and verification of Scala programs (EPFL)
- [Eldarica](http://lara.epfl.ch/w/eldarica) (Java): predicate abstraction engine, generates Abstract Reachability Tree (ART) using lazy abstraction (EPFL)
    * [Eldarica-P](http://www.philipp.ruemmer.org/eldarica-p.shtml) (?, Java): reachability checker for unbounded Petri nets (EPFL)
- [Bug-Assist](http://bugassist.mpi-sws.org/) (?): error localization in ANSI-C solving MAX-SAT (Max Planck Inst.)
- [CADP](http://www.inrialpes.fr/vasy/cadp.html) (FUSC): compilers, equivalence checking tools, model-checkers for temporal logics & μ-calculus, verifications: enumerative, on-the-fly, symbolic using BDD, etc. (INRIA)
- [MONA](https://github.com/cs-au-dk/MONA) (GPL-2, C/C++): Decision procedure for monadic second-order logic on finite strings and trees ([Aarhus Univ.](http://www.brics.dk/mona))
- [Boom](http://www.cprover.org/boom/) (BSD): Model checking of Boolean programs (ETHZ, Oxford Univ.)
- [MCTK](http://www.kailesu.net/MCTK/) (LGPL, C): model checker for epistemic logic as modification of CUDD and NuSMV ([Griffith Univ.](http://www.kailesu.net/))
- [SMCDEL](https://github.com/jrclogic/SMCDEL) (GPL-2, Haskell):  model checker for Dynamic Epistemic Logic. (ILLC, University of Amsterdam)
- [SymDIVINE](https://github.com/yaqwsx/SymDIVINE) (MIT, C++): a tool for control explicit/data symbolic bit-precise LTL verification of parallel C/C++ programs using LLVM bitcode as intermediate representation [Masaryk Univ.](http://anna.fi.muni.cz/~xbauch/symdivine.html)
- [IC3](https://github.com/arbrad/IC3ref) (MIT, C++): IC3 reference implementation ([Stanford](http://theory.stanford.edu/~arbrad/))
- [Overture](https://github.com/overturetool/overture) (GPL-3.0, Java): An IDE for developing and analyzing VDM models.
- [Smallfoot](http://www0.cs.ucl.ac.uk/staff/p.ohearn/smallfoot/) (QPL, OCaml): Automatic verification tool that checks separation logic specifications of sequential and concurrent programs that manipulate recursive dynamically-allocated (linked) data structures.
- [Cave](https://people.mpi-sws.org/~viktor/cave/) (BSD-style, OCaml): automated verification tool for proving memory safety and linearizability (that is, atomicity and functional correctness) of concurrent data structures
- [sally](http://sri-csl.github.io/sally/) (GPLv2, [C++](https://github.com/SRI-CSL/sally)): Model checker for infinite-state systems described as transition systems, includes BMC, k-induction, IC3 (SRI/CSL)
- [Sviss](http://www.cs.ox.ac.uk/people/thomas.wahl/Sviss/) (?, C++): Symbolic CTL model checker with symmetry reduction, using CUDD 2.4.1 (ETHZ, UT Austin, Univ. of Oxford)

## logic -> automata & automata tools

### LTL -> *BA
- [ltl2ba](http://www.lsv.ens-cachan.fr/~gastin/ltl2ba/index.php): LTL -> BA (ENS de Cachan)
    * [LTL2BA4J](http://www-i2.informatik.rwth-aachen.de/Forschung/RV/ltl2ba4j/index.html) (GPL-3, Java): version of ltl2ba for Java
    * [ltl3ba](http://sourceforge.net/projects/ltl3ba/) (GPL-2, C): LTL -> BA ([Masaryk Univ.](http://is.muni.cz/th/143254/fi_r/thesis_proposal.pdf))
- [LTL -> NBA](http://www.ti.informatik.uni-kiel.de/~fritz/) (Python)
- [lbtt](http://www.tcs.hut.fi/Software/lbtt/) (GPL): tool for testing programs translating LTL -> BA
- [Wring](http://www.ist.tugraz.at/staff/bloem/wring.html) (Perl): LTL -> GBA (TU Graz)
- [Temporal Massage Parlor](http://www.bell-labs.com/project/TMP/): Optimized Translator of an Extended Linear Temporal Logic into Büchi automata and Promela (Bell Labs)
- [LBT](http://www.tcs.hut.fi/Software/maria/tools/lbt/): LTL-> BA
- [ltl2tgba](http://spot.lip6.fr/userdoc/ltl2tgba.html): LTL or PSL-> Transition-based GBA | BA (part of SPOT)
- [LTL2AUT](http://www.cs.rice.edu/CS/Verification/Software/software.html) (C++): LTL-> BA
- [DBA Minimizer](http://www.react.uni-saarland.de/tools/dbaminimizer/) (FUSC, C++): uses external SAT solver for DBA minimization
- [Wring](http://www.iaik.tugraz.at/content/research/design_verification/wring/) (Perl): translate LTL  formulae to generalized Buechi automata (TU Graz)
- [GOAL](http://goal.im.ntu.edu.tw/): graphical interactive tool for defining and manipulating Büchi automata and temporal logic formulae (NTU)
- [LTL -> Buchi Genealogy](http://spot.lip6.fr/wiki/LtlTranslationAlgorithms) ([EPITA](http://www.lrde.epita.fr/~adl/))
- [LTSA](http://www.doc.ic.ac.uk/ltsa/) (?, Java): Labelled Transition System Analyzer ([Imperial College London](http://www-dse.doc.ic.ac.uk/cgi-bin/moin.cgi/jnm))
    * [OLTSA](https://www-roc.inria.fr/arles/index.php/software/197-oltsa-ontology-based-labeled-transition-system-analyzer): ontology-based LTSA extension (INRIA)
- [WDBA](http://www.daxc.de/eth/wdba/index.html) (BSD, OCaml): Reads safety property BA and negation BA as SPIN never claims -> outputs weak deterministic BA ([ETHZ](http://www.daxc.de/eth/))
- [psl2ba](https://code.google.com/p/psl2ba/) (BSD-3, OCaml/uses CUDD): Translator from Property Specification Language (PSL) or LTL -> BA for SMV or SPIN ([ETHZ](http://www.daxc.de/eth/))
- [rltl2ba](https://github.com/juliansf/rltl2ba) (BSD, OCaml/C++/uses psl2ba, CUDD): Translator from Regular LTL (RLTL) -> BA ([IMDEA](http://software.imdea.org/~julian/))
- [aalta](http://www.lab205.org/aalta/): LTL -> BA using obligation sets (East China Normal Univ.)

### LTL -> DRA
- [ltl2dstar](http://www.ltl2dstar.de/) (GPL): LTL -> DRA (deterministic Rabin) ([Univ. Bonn](http://www.ltl2dstar.de/literature/ltl2dstar-diploma-thesis.pdf))
    * [online interface](http://www.cds.caltech.edu/~slivings/sandbox/wrapltl.php) ([Caltech.CDS](http://scottman.net/))
- [Rabinizer](https://www7.in.tum.de/~kretinsk/rabinizer3.html) (Disclaimer, Java): LTL -> DRA with generalized Rabin pairs ([TUM](https://www7.in.tum.de/~kretinsk/))
- [LTL3DRA](https://sourceforge.net/projects/ltl3dra/) (GPL-2, C): fragment of LTL -> DRA based on LTL3BA (Masaryk Univ.)

### other
- [dk.brics.automaton](http://www.brics.dk/automaton/): DFA/NFA implementation with UTF16 alphabet & support for (&non-) standard regexp
- [FSA function library](http://users.isr.ist.utl.pt/~pal/cadeiras/deds0708/deds/MatlabFSA.zip) (MATLAB): [doc here](http://users.isr.ist.utl.pt/~pal/cadeiras/deds0708/deds/Projects06-07/BLacerda.pdf) ([ISR-Lisbon](http://users.isr.ist.utl.pt/~blacerda/))
- [Hessen](http://forsyte.at/software/automata/) (?, C++): Automata Library (TU Wien)
- [FSME, FSMC, FSMD](http://sourceforge.net/projects/fsme/) (GPL-2, Qt): FSM editor, compiler, debugger for drawing, exports: `XML` | C++ | Python
- [Kermeta](http://www.kermeta.org/) (EPL): Metamodel programming environment: editor, OCL, compiler to Java | OSGI, kermeta <-> ecore | XMI ([IRISA](http://triskell.irisa.fr/?set_language=en&cl=en))
- [Papyrus](http://www.papyrusuml.org/scripts/home/publigen/content/templates/show.asp?L=EN&P=55&vTicker=alleza&ITEMID=3) (EPL): Graphical UML2 modeling in Eclipse ([CEA LIST](http://www-list.cea.fr/))
- [Topcased](http://www.topcased.org/) (EPL): Graphical editors for: Ecore, UML, SAM, AADL, SysML, and doc generator, model transformations (INRIA)
    * [Topcased verification tools](http://www.topcased.org/index.php?idd_projet_pere=55)
- [MARTE](http://www.omgmarte.org/): UML extension for model-driven development of real-time and embedded systems (OMG)
- [timesquare](http://timesquare.inria.fr/) (EPL): Model development kit as Eclipse plugings based on formal Clock Constraint Specification Language (CCSL) to manipulate logical time (INRIA)
- [libalf](http://libalf.informatik.rwth-aachen.de/) (LGPL-3, C++/C/Java): Learning finite-state automata: DFA: Angluin's L\*, L\* (adding counter-examples to columns), Kearns / Vazirani, Rivest / Schapire, Regular positive negative inference (RPNI), Biermann & Feldman's algorithm (using SAT-solving), and NFA: NL\*, DeLeTe2, Biermann & Feldman's (RWTH Aachen Univ., ENS Cachan, TU Munchen)
    * [AMoRE](http://amore.sourceforge.net/) (GPL-2, C/Java): Automata, Monoids, and Regular Expressions (RWTH Aaachen Univ., Univ. Kiel)
    * [libmVCA]
    * [liblangen]
    * [finite automata tool]
- [APHMIN](http://depend.cs.uni-sb.de/tools/aphmin/) (?, ?): Tools to generate, manipulate, and minimize acyclic phase-type representations (Saarland Univ.)
- [FlowSim](http://depend.cs.uni-sb.de/tools/flowsim/) (GPL-3, ?): Measure resources needed to find maximal strong simulation relation for a model under different optimizations (Saarland Univ.)
- [fc2symbmin](http://www-sop.inria.fr/meije/personnel/Michel.Bourdelles/tutorial.html#Section1): Finite State Mealy Machine analyzer (INRIA)
- [PyFMI](https://pypi.python.org/pypi/PyFMI/) (LGPL-3, Python): Load and interact with Functional Mock-Up Units ([FMU](https://www.fmi-standard.org/))
- [FMU SDK](https://github.com/mtiller/fmusdk) (?, C): FMU SDK (Qtronic)
- [hoaf](https://github.com/adl/hoaf) (?, text): Text file format for omega-automata (Masaryk Univ., EPITA, IST Austria, TU Dresden)
- [JFLAP](http://www.jflap.org/): experiment with NFA, NPA, multi-tape Turing machines
- [ltlmp_sat](https://github.com/nothymr/ltlmp_sat) (?, Python): LTL mean-payoff satisfiability checker
- [LtlSharp](https://github.com/ancailliau/LtlSharp) (MIT, C\#): Library for parsing and manipulating LTL formulae (U Catholique Louvain)

## Term rewrite systems
- [Autowrite](http://dept-info.labri.fr/~idurand/autowrite/) (?, Lisp): check properties of term rewrite systems and manipulate tree automata
- [Timbuk](http://www.irisa.fr/celtique/genet/timbuk/) (GPL-2, OCaml): Tools for reachability proofs over term rewriting systems and manipulate bottom-up non-deterministic finite tree automata (IRISA)
- [JITty](http://wwwhome.cs.utwente.nl/~vdpol/jitty/README) (C): term rewriter with strategy annotations
- [K](http://www.kframework.org/index.php/Main_Page): rewrite-based executable semantic framework (UIUC)
- [ELAN](http://elan.loria.fr/): Rule based programming using strategic rewriting (LORIA)

## Open Systems

### Synchronous Languages
Synthesis in this context refers to compilation from source, not from temporal logic.
This distinguishes it from synthesis from temporal logic by solving games.
In some sense the latter is from an "even more declarative" problem description.

#### Imperative
- [Esterel](http://en.wikipedia.org/wiki/Esterel), [old](http://www-sop.inria.fr/meije/esterel/esterel-eng.html): Synchronous reactive programming language & compiler to FSM (C language), Graphical symbolic debugger, explicit/BDD verification for bisimulation reduction | safety checking (Ecole des Mines de Paris, INRIA)
    * [CEC](http://www1.cs.columbia.edu/~sedwards/cec/) (BSD-3, C++/ANTLR): Esterel V5 compiler to C | Verilog | BLIF ([Columbia](http://www.cs.columbia.edu/~sedwards/))
    * [scdata](http://www-sop.inria.fr/meije/esterel/scdata.html) (?): Boolean datapath generator for Esterel: translates action calls in sc code over boolean variables into standard nets also in sc (INRIA, Ecole des Mines de Paris)
    * [Ocjava](http://www-sop.inria.fr/meije/esterel/ocjava.html) (?): Esterel Java code generator (INRIA)
- [Quartz](http://rsg.cs.uni-kl.de/publications/datarsg/Schn09.pdf): derivative of Esterel that includes:
        * non-determinism
        * asynchronous execution
        * hybrid systems
    (Kaiserslautern Univ.)
    * [Averest](http://en.wikipedia.org/wiki/Averest): Synchronous programming language Quartz and compiler to TS, symbolic model checker, tool for hardware/software synthesis from Quartz ([TU Kaiserslautern](http://es.informatik.uni-kl.de/))
- [Xeve](http://www-sop.inria.fr/meije/verification/Xeve/): Esterel verification environment (INRIA)

#### Declarative
- [Lustre](http://en.wikipedia.org/wiki/Lustre_%28programming_language%29): Declarative, synchronous dataflow programminglanguage for reactive systems
    * [Lustre](https://github.com/ladace/Lustre) (?, OCaml): Lustre interpreter
    * [MATOU](http://www.cfdvs.iitb.ac.in/download/Docs/verification/tools/kronos/Verimag_Home_Page/PEOPLE/Florence.Maraninchi/MATOU/index.phtml) (?): Implementation of mode-automata on top of Lustre (VERIMAG)
        * [KIND](http://clc.cs.uiowa.edu/Kind/) (BSD-3, OCaml): K-induction based for safety properties of Lustre programs, Automatic invariant generation, parallel: PKIND (Univ. Iowa, NASA/CMU, ONERA)
    * [KIND2](http://kind2-mc.github.io/kind2/) (Apache-2, OCaml/C++): Successor of KIND (Univ. Iowa)
    * [Zustre](https://github.com/coco-team/zustre) (BSD-3, Python): SMT-based PDR-style verification engine for Lustre programs, also an engine for generating assume/guarantee contracts (NASA/CMU/SEI)
- [NBAC](http://pop-art.inrialpes.fr/~bjeannet/nbac/index.html) (OCaml): Co-/Reachability, slicing of synchronous deterministic reactive systems with Boolean, numerical variables (VERIMAG)
    * [`lus2nbac`](http://pop-art.inrialpes.fr/~bjeannet/nbac/index_6.html): Convert Lustre to NBAC (VERIMAG)
    * [`nbac2lucky`](http://pop-art.inrialpes.fr/~bjeannet/nbac/index_7.html): Convert counterexamples to Ludic debugger (VERIMAG)
    * [`autoc2auto`, `auto2nbac`, `nbac2auto`](http://pop-art.inrialpes.fr/~bjeannet/nbac/index_8.html):  Analyze AUTOC/AUTO hybrid automata (VERIMAG)
- [SIGNAL](http://en.wikipedia.org/wiki/SIGNAL_programming_language): Synchronized data-flow programming language for systems with multiple clocks ([INRIA](http://www.irisa.fr/espresso/home_html))
    * [Polychrony / SME](http://www.irisa.fr/espresso/Polychrony/) (GPL, Eclipse Public License): SIGNAL IDE (IRISA)
- [Sigali](http://www.irisa.fr/vertecs/Softwares/sigali.html), [old](http://www.irisa.fr/vertecs/Logiciels/sigali.html) (FUSC): Model check implicit labeled transition systems (INRIA)
- [TGV](http://www.irisa.fr/vertecs/Softwares/TGV.html) (?): Generation of conformance test suites for protocols, based on I/O transition systems (IOLTS) (IRISA)
- [abc] (www.eecs.berkeley.edu/~alanmi/abc/abc.htm) (?, C): a growing software system for synthesis and verification of binary sequential logic circuits appearing in synchronous hardware designs; ABC combines scalable logic optimization based on And-Inverter Graphs (AIGs), optimal-delay DAG-based technology mapping for look-up tables and standard cells, and innovative algorithms for sequential synthesis and verification

#### Statecharts
- [PlayGo](http://www.weizmann.ac.il/mediawiki/playgo/index.php/Main_Page) (Weizmann Inst.)
- [Time Rover](http://www.time-rover.com/)
- [SyncCharts](http://en.wikipedia.org/wiki/SyncCharts): Graphical formalism for reactive modeling ([Univ. Nice Sophia-Antipolis](http://www-sop.inria.fr/members/Charles.Andre/))
    * [SPORTS Project](http://www.i3s.unice.fr/~map/WEBSPORTS/SyncCharts/) (FUSC): SyncCharts tools
    * [SCC](http://julien.boucaron.free.fr/i3s/)): SyncCharts Compiler Collection for XML | BLIF | C output (Univ. Nice Sophia-Antipolis, INRIA)



# Synthesis

## Open Systems (Games: System & UnControlled Environment)


### Discrete games

#### [GR(1) games](http://dl.acm.org/citation.cfm?id=2146252) (= Generalized Reactivity 1)
- [gr1c](https://github.com/tulip-control/gr1c) (BSD-3, C, uses CUDD): checking realizability of and synthesizing strategies for GR(1) specifications & much more ([Caltech.CDS](http://scottman.net/))
- [slugs](https://github.com/LTLMoP/slugs) (BSD-3, C++, uses CUDD): a stand-alone reactive synthesis tool for GR(1) synthesis (Cornell)
- [JTLV](http://sourceforge.net/projects/jtlv/) (LGPL-2, Java/C)
    * [TLV](http://www.cs.nyu.edu/acsys/tlv/): predecessor of JTLV
- [RATSY](http://rat.fbk.eu/ratsy/) (LGPL-2+, Python/PyGTK): PSL | BA specs -> gr1 synthesis, game-based debug approach, circuit synthesis ([TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
    * [Anzu](http://www.iaik.tugraz.at/content/research/design_verification/anzu/) (Perl, uses CUDD): synthesizes Verilog ([TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
    * [RAT](http://rat.fbk.eu/) (?, Python): RATSY's pedecessor (FBK, [TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
    * marduk (Python, needs NuSMV): game solver used by RATSY
- [NuGAT](https://es.fbk.eu/index.php?n=Tools.NuGaT) (LGPL-2+): Game solver on top NuSMV
    * [chameleon-debaets](https://code.google.com/p/chameleon-nugat-api/) (GPL-3, Java): Java interface to NuGAT
- [AspectLTL](http://aspectltl.ysaar.net/wiki/index.php?title=AspectLTL) (?, Java): Aspect programming paradigm language (Weizmann Inst. Science)
- [open Promela](https://github.com/johnyf/openpromela) (BSD-3, Python): synthesize reactive(1) designs from multi-paradigm specifications written in an extension of Promela for open systems ([Caltech](http://www.cds.caltech.edu/~ifilippi/))

#### Full LTL games
- [Acacia+](http://lit2.ulb.ac.be/acaciaplus/) (GPL, Python/C): LTL Realizability check & winning strategy synthesis using AntiChains [repo](https://code.google.com/p/ltlsynthesis/) (Univ. Mons)
    * [Acacia](http://lit2.ulb.ac.be/acacia/) (GPL-2, Perl)
    * [Alaska](http://lit2.ulb.ac.be/alaska/) (GPL-2, Python): Antichains for Logic, Automata and Symbolic Kripke structure Analysis (predecessor of Acacia) ([ULB](http://www.ulb.ac.be/di/ssd/madewulf/))
    * [jorro](https://github.com/cloverrose/jorro) (?, Java/Perl): visualize transition systems synthesized by Acacia+ and Lily
    * [ltl2aig](https://github.com/gaperez64/acacia_ltl2aig/blob/master/ltl2aig.py) (GPL, Python): LTL -> And-inverter graph format
- [Lily](http://www.iaik.tugraz.at/content/research/design_verification/lily/) (Perl): synthesizes from PSL | LTL & I/O signal partition, works on top of Wring, outputs VERILOG | dot (TU Graz)
- [GAVS+](http://www6.in.tum.de/~chengch/gavs/) (GPL-3, Java): visualize algorithmic games used in verification and synthesis (TU Munchen)
- [Unbeast](http://www.react.uni-saarland.de/tools/unbeast/) (C++, FUSC) symbolic bounded synthesis, depends on either `ltl2ba` or `spot` (Saarland Univ.)
- [GASt](http://automata.rwth-aachen.de/research/GASt/) experimental platform:
    * NBA determinization:
        + Safra
        + Muller-Schupp
        + improved Muller-Schupp
        + Miyano/Hayashi breakpoint construction
    * game synthesis:
        + reachability
        + safety
        + weak parity
        + Staiger-Wagner
        + request-response
        + Buchi
        + generalized Buchi
        + parity
        + Muller
        + simple Streett
        + Streett
        + mean payoff
    * live sequence charts

    (RRWTH Aaachen)
- [party-elli](https://github.com/5nizza/party-elli) (MIT, Python): SMT based bounded synthesis (TU Graz)
- [Rabin](https://github.com/filipbartek/rabin) (?, C++): Rabin game solver ([Masaryk Univ.](https://github.com/filipbartek))
- [BoSy](https://www.react.uni-saarland.de/tools/bosy/) (Swift): Constraint-based (SAT,SMT,QBF,DQBF) bounded synthesis (Saarland Univ.)

#### Safety specs (controller synthesis)
- [AbsSynthe](https://github.com/gaperez64/AbsSynthe) (GPL-3, C/Python): controller synthesis from succinct safety specs
- [demiurge](https://www.iaik.tugraz.at/content/research/opensource/demiurge/) (GLGPL3, C++): SAT based controller synthesizer from SYNTCOMP specs (TU Graz)
- [SafetySynth](https://www.react.uni-saarland.de/tools/safetysynth/) (Swift): symbolic BDD-based safety game solver for SYNTCOMP (Saarland Univ.)
- [Reglisse](https://github.com/romainbrenguier/Reglisse) (GPL-2, OCaml): Generate hardware description from safety conditions given by regular languages

#### Parity Game solvers
- [PGSolver](http://www2.tcs.ifi.lmu.de/pgsolver/) (OCaml): tools for generating, manipulating and solving parity games (Univ. Muchich, Univ. Kassel)
- [PDSolver](http://www.cs.ox.ac.uk/matthew.hague/pdsolver.html) (OCaml): evaluating both mu-calculus formulas over pushdown systems and pushdown parity games (Oxford Univ.)
- [alpaga](http://lit2.ulb.ac.be/alpaga/) and [github](https://github.com/madewulf/alpaga) (Python, uses PyCUDD): solver parity games with imperfect information using antichains ([ULB](http://www.ulb.ac.be/di/ssd/madewulf/))
- [oink](https://github.com/trolando/oink) (Apache-2.0, C++): High-performance implementations of state-of-the-art algorithms representing different approaches to solving parity games (JKU)

#### Quantitative games
- [Quasy](http://pub.ist.ac.at/quasy/) (Scala, Java, C++): Quantitative synthesis of reactive systems from qualitative & quantitative GOAL specs, in/out: GOAL format (IST Austria)
- [GIST](http://pub.ist.ac.at/gist/index.html) (?): solving probabilistic games with ω-regular objectives qualitatively (IST Austria)
- [mpg-solver](https://github.com/gaperez64/mpg-solver) (GPL-2, C/C++/Python): Mean-payoff game solver ([Univ. Libre de Bruxelles](http://www.ulb.ac.be/di/verif/gaperez/))

#### Other
- [MLSolver](https://github.com/tcsprojects/mlsolver) (?, OCaml): solving the satisfiability and validity problems for modal fixpoint logics (Univs. Munich, Kassel)
- [`aisy`](https://bitbucket.org/art_haali/aisy-classroom) (?, Python): safety synthesis from AIGER circuits format, using PyCUDD
- [BluSTL](https://github.com/BluSTL) (BSD-3, MATLAB): BluSTL (pronounced "blue steel") is a MATLAB toolkit for automatically generating hybrid controllers from specifications written in Signal Temporal Logic.
- [G4LTL-ST] (http://sourceforge.net/projects/g4ltl/) (BSD, Java): automatically generates industrial control software (supporting IEC-61131-3 Structure Text) from extended logic specifications.

### Hybrid games
- [TuLiP](https://github.com/tulip-control/tulip-control) (BSD-3, Python): Receding Horizon Temporal Logic Planning Toolbox ([Caltech.CDS](http://www.cds.caltech.edu/~murray/wiki/Main_Page))
- [LTLMoP](http://ltlmop.github.io/) (GPL-3, Python): designing, testing, and implementing hybrid controllers generated automatically from task specifications written in Structured English or Temporal Logic ([Cornell](http://cornell-asl.org/wiki/index.php?title=Main_Page))
    * [SLURP](https://github.com/PennNLP/SLURP) (GPL-3, Python): situation and language understanding robot platform, uses LTLmop (UPenn)
- [Tools from Boston Univ.](http://hyness.bu.edu/Software.html) (?, MATLAB)
- [Tools from Saarland University](http://react.cs.uni-sb.de/tools/) (Saarland Univ.)
- [Synthia](http://www.react.uni-saarland.de/tools/synthia/) (GPL-3, C/C++): Verification certificates (deductive proofs) and synthesis for partially implemented systems, abstraction refinement ([Saarland Uni.](http://www.react.uni-saarland.de/people/peter.html))
- [PESSOA](https://sites.google.com/a/cyphylab.ee.ucla.edu/pessoa/home) (FUSC, MATLAB): synthesis of correct-by-design embedded control software based on approximate bisimulations (UCLA)
- [TALIRO](https://sites.google.com/a/asu.edu/s-taliro/) (GPL, MATLAB) ([ASU](http://www.public.asu.edu/~gfaineko/))
- [SCOTS](https://gitlab.lrz.de/matthias/SCOTSv0.2) (BSD-3, C++/MATLAB): computation of discrete abstractions and symbolic controllers (TUM)
- [ARCS](https://github.com/pettni/abstr-refinement) (MIT, C/MATLAB): abstraction-refinement-based incremental synthesis for switched systems (Univ. of Michigan)

### Contracts
- [Mica](http://www.irisa.fr/s4/tools/mica/Mica__A_Modal_Interface_Compositional_Analysis_Library/Introduction.html) (CeCILL-C-1, OCaml):  Modal Interface algebra for contract based design ([INRIA/IRISA](http://www.irisa.fr/prive/Benoit.Caillaud/Benoit_Caillauds_Professional_homepage/Welcome.html))
- [OCRA](https://es-static.fbk.eu/tools/ocra/index.php?n=Main.HomePage) (closed, ?): verification of logic-based contract refinement, uses NuSMV3 (Bruno Kessler Found.)
    * [AF3-OCRA](https://es-static.fbk.eu/tools/autofocra/): OCRA plug-in for Autfocus
    * [FoReVer](https://es-static.fbk.eu/projects/forever/index.php?n=Main.Links)

### Hardware
- [Yosys] (https://github.com/cliffordwolf/yosys) (ISC, C++): a framework for RTL synthesis tools
- [Clash] (http://www.clash-lang.org/) (?, Haskell) generates VHDL from Haskell
- [Lava] (https://hackage.haskell.org/package/kansas-lava) (?, Haskell): generates circuits from FSMs, behavioural specs (VHDL, Verilog) + verif via NuSMV
- [Chisel] (https://github.com/ucb-bar/chisel/) (?, Scala): supports advanced hardware design using highly parameterized generators and layered domain-specific hardware languages; Chisel can generate a high-speed C++-based cycle-accurate software simulator, or low-level Verilog designed to pass on to standard ASIC or FPGA tools for synthesis and place and route

### Other
- [Times](http://www.timestool.com/) (?): Tool for Modeling & Implementation of Embedded Systems (GUI editor, simulator, verifier for schedulability analysis) (Uppsala Univ.)
- [BigMC](https://github.com/bigmc/bigmc) (GPL, C++/C/PHP/...): Bigraphical reactive systems (IT Univ. Copenhagen)
- [Ticc](http://code.google.com/p/ticc/) (GPL-2, ?): Interface compatibility and composition, components specify own behavior and that expected by others, CTL properties checked and propagated (UCSC)



# Timed Systems
- [UPPAAL](http://www.uppaal.org/), [UPPAAL-Tiga](http://people.cs.aau.dk/~adavid/tiga/) (FUSC): Timed automata (Uppsala Univ., Aalborg Univ.)
    * [manipulate UPPAAL XML](https://launchpad.net/pyuppaal) (GPL-3, Python)
    * [Yggdrasil](http://www.quasimodo.aau.dk/tools.html) (?, ?): UML (subset) -> Uppaal, intended for test generation (Aalborg Univ.)
    * [METAMOC](http://metamoc.dk/) (GPL-3, Python): WCET Analysis of ARM Processors using Real-Time model-checking (Aalborg Univ.)
    * [SARTS](http://www.sarts.dk/old.php) (?, Java): Model Based Schedulability Analysis of Real-Time Systems, SCJ2, UPPAAL (Aalborg Univ.)
    * [`udbml`](https://github.com/osankur/udbml) (AGPL-3, C++/OCaml): OCaml wrapper for the [Uppaal DBM library](http://people.cs.aau.dk/~adavid/UDBM/) of efficient data structures to represent clock constraints in timed automata
- [OPAAL](https://launchpad.net/opaal) (GPL-3, Python): distributed/parallel (discrete time) model checker for networks of timed automata  using MPI
- [ECDAR](http://people.cs.aau.dk/~adavid/ecdar/) (FUSC): timed interface theory (Aalborg, INRIA, ITU)
- [PyECDAR](https://project.inria.fr/pyecdar/) (GPL-2, Python): solve timed games based on timed automata models (ITU)
- [IOA](http://groups.csail.mit.edu/tds/ioa/) (MIT, Java): I/O automata formal language (MIT)
- [TEMPO](http://www.veromodo.com/) (closed, Java): Formal language for modeling distributed systems w/ | w/o timing constraints as collections of interacting state machines, i.e., timed input/output automata (TIOA) (UIUC)
    * [Tempo2HSal](http://www.csl.sri.com/users/tiwari/VVFCS.html) (?, Python): Tempo (`.tioa`) -> HybridSAL (`.hsal`) translator (SRI)
- [ATAS](http://sourceforge.net/projects/atao/) (GPL-3, Python): Alternating 1-clock (fully decidable) Timed Automata Solver
- [PPL binding](https://launchpad.net/pyppl) (GPL-2, Python): for [Parma Polyhedral Lib](http://bugseng.com/products/ppl) features some specific methods for Timed Automata analysis
- [MCPTA](http://www.modestchecker.net/) (FUSC, ?): Probabilistic Timed Automata model checker for MoDeST | UPPAAL | PRISM - maps on PRISM (Saarland Univ.)
- [SAAtRE](http://symbolaris.com/info/saatre.html) (?): Abstraction refinement model checker for Timed Automata based on extended SAT-solving, UPPAAL-like input format (Univ. Oldenburg, CWI)
- [Fortuna](http://www.cs.ru.nl/J.Berendsen/fortuna/) (GPL-3, C++/Eclipse): MC priced probabilistic timed automata (PPTAs) (Univ. Twente)
- [COSPAN](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.39.8153) (?, ?): Automata-theoretic verification of coordinating processes with timing constraints (UPenn)
- [Romeo](http://romeo.rts-software.org/?page_id=2): timed Petri nets (IRCCyN)
- [ExSched](http://www.idt.mdh.se/~exsched/): develop operating system schedulers for VxWorks and Linux w/o modifying the underlying kernel ([Malardalen Univ.]http://www.es.mdh.se/staff/197-Mikael__sberg))
- [RTComposer](http://www.cs.bgu.ac.il/~geraw/rtcomposer.html) (Java): classes and utilities for predictable real-time scheduling (BenGurion, UPenn)
- [ASTRAL](http://dimacs.rutgers.edu/Workshops/Security/program2/kemmerer/index.html): MC of real-time systems (UCSB)
- [PAT](http://pat.sce.ntu.edu.sg/?page_id=2602) (?, C\#): simulator, MC, refinement checker for concurrent and RT systems (Nanyang Tech. Univ.)
- [HCMC](http://www.lsv.ens-cachan.fr/~fl/cmcweb.html) (? , C++): Compositional model checking for real-time systems (ENS-Cachan)
- [IMITATOR] (http://www.imitator.fr/index.html) (GPL, Python?): is a tool for parametric verification and robustness analysis of real-time systems. It relies on the formalism of networks of parametric timed automata, augmented with integer variables and stopwatches.
- [CoVerTS] (https://github.com/astefano/CoVerTS) (Scala): compositional verification of state properties for timed systems

# Hybrid Systems
- [Ptolemy](http://ptolemy.eecs.berkeley.edu/index.htm) (BSD-3, Java): modeling, simulation, and design of concurrent, real-time, embedded systems (UC Berkeley)
- [HyLink](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HyLink) (FUSC, Python): Restricted Simulink/Stateflow models -> HyXML-> HyTech | UPPAAL (UIUC)
- [CHARON](http://rtg.cis.upenn.edu/mobies/charon/) (?, Java): Language and implementation (editor, model browser, visual simulator) for modular specification of interacting hybrid systems based on the notions of agent and mode (UPenn)
- [CARTS](http://rtg.cis.upenn.edu/carts/) (FUSC, Java): Compositional Analysis of Real-Time Systems (UPenn)
- [START](http://www.andrew.cmu.edu/user/arieg/Rek/): time-bounded static analysis of concurrency properties of Real-Time Embedded Software
- [IF](http://www-verimag.imag.fr/~async/IF/index.html) (FUSC): static analysis, model-checking, test generation, [Open-Kronos](http://www-verimag.imag.fr/~tripakis/openkronos.html), [Kronos](http://www-verimag.imag.fr/DIST-TOOLS/TEMPO/kronos/): TCTL verification of Timed Automata (VERIMAG)
- [CIF](http://cif.se.wtb.tue.nl/): Compositional Interchange Format for Hybrid Systems toolset
- [Passel](http://publish.illinois.edu/passel-tool/) (closed, C#/Python): invariant synthesis and inductive invariant proving (UIUC)
- [Rabbit](http://www.sosy-lab.org/~dbeyer/Rabbit/) (Apache): RTS modular spec: timed (and hybrid) automata: CottbusTimed Automata, MC for reachability analysis and refinement check (Bradenburg TU)
- [Mobius](https://www.mobius.illinois.edu/) (?, Java/C++): Model-based environment for validation of system reliability, availability, security, and performance ([UIUC](https://www.perform.csl.illinois.edu/))
- [HYMITATOR] (GLP, OCaml) (https://lipn.univ-paris13.fr/~andre/software/hymitator/):  is a tool dedicated to the synthesis of parameters for hybrid automata

## Linear
- [HyTech](http://embedded.eecs.berkeley.edu/research/hytech/) (FUSC, C): computes condition under which a linear hybrid system satisfies a temporal requirement (UC Berkeley)
- [d/dt](http://www-verimag.imag.fr/~tdang/ddt.html) (?, ?): Reachability analysis of Continuous and Hybrid Systems with linear differential inclusions ([VERIMAG](http://www-verimag.imag.fr/~tdang/))
- [HARE](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HARE) (?): Abstraction refinement for safety
- [PHAVer](http://www-verimag.imag.fr/~frehse/phaver_web/) (GPL-2, C++): verifying safety properies of hybrid systems (exact arithmetic, on-the-fly over-approximation of PWA dynamics, compositional & assume-guarantee reasoning) ([Verimag](https://sites.google.com/site/frehseg/))
    * [vim highlight](http://www.vim.org/scripts/script.php?script_id=3256), its [github](https://github.com/vim-scripts/phaver)
    * [ProHVer](http://depend.cs.uni-sb.de/tools/prohver/) (GPL-3, C++): Unbounded reachability probability for probabilistic hybrid automata (Univ. Saarland)
- [CheckMate](http://www.mathworks.com/matlabcentral/fx_files/15441/3/content/doc/main.htm) (MATLAB) modeling, simulation & investigation, [demos](http://www.mathworks.com/matlabcentral/fileexchange/17004-checkmate-demos)
- [HYSDEL](http://control.ee.ethz.ch/~hybrid/hysdel/) (GPL, C++/MATLAB): (Hybrid Systems Description Language) HYSDEL -> MLD compiler, also language to model interconnected linear systems and automata (ETHZ)
- [Hybrid Toolbox for MATLAB](http://cse.lab.imtlucca.it/~bemporad/hybrid/toolbox/) (FUSC, MATLAB/Simulink): Modeling, simulation, verification, constrained MPC, generate linear & hybrid MPC PWA control laws ([IMT Lucca](http://cse.lab.imtlucca.it/~bemporad/Alberto_Bemporads_Home_Page/Home_Page.html))
- [Ellipsoidal Toolbox for MATLAB](http://code.google.com/p/ellipsoids/) (BSD-3, MATLAB): External and internal ellipsoidal approximations of geometric (Minkowski) sums and differences of ellipsoids, intersections of ellipsoids and intersections of ellipsoids with halfspaces and polytopes; distances between ellipsoids, between ellipsoids and hyperplanes, between ellipsoids and polytopes; and projections onto given subspaces. For forward and backward reach sets of continuous- and discrete-time PWA systems (UC Berkeley)
- [MATISSE](http://www-ljk.imag.fr/membres/Antoine.Girard/Software/Matisse/) (GPL-3, MATLAB): Approximate bisimulations: safety verification and reachable set computation of large dimensional, constrained linear systems. Needs: MPT, YALMIP, SEDUMI (UPenn, IMAG)
- [BACH](http://seg.nju.edu.cn/BACH/): bounded model checker for Linear Hybrid Systems (Nanjing Univ.)
- [`tltk-mtl`](https://pypi.org/project/tltk-mtl) (?, Python): tool for computing Metric Temporal logic robustness

## Non-Linear
- [HTV](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HTV) (closed, MATLAB): verify systems from their simulation and run-time traces using imprecise samples and possibly incomplete models to compute overapproximations of bounded reach sets (UIUC)
- [SpaceEx](http://spaceex.imag.fr/) (GPL-3, C++): Reachability & safety verification (Verimag, Lab Jean Kuntzmann, DGA-MI)
- [Ariadne](http://trac.parades.rm.cnr.it/ariadne/) (GPL-3, C++/Python): Dynamical systems set-based analysis (reachability analysis, robust simulation, safety verification - reset, flow, guard predicates given by nonlinear functions) (Univ. Udine, PARADES, CWI, Univ. Verona)
- [MPT](http://control.ee.ethz.ch/~mpt/2/about.php) (GPL, MATLAB): Design, analysis and deployment of optimal controllers for constrained linear, nonlinear and hybrid systems (ETHZ)
- [HybridSal](http://sal.csl.sri.com/hybridsal/) (GPL-2, LISP/Java): Language extension to SAL for specifying Hybrid Systems & hybrid abstraction tool to discrete SAL specifications for model checking with other SAL tools ([SRI](http://www.csl.sri.com/users/tiwari/))
    * [Relational Abstraction](http://www.csl.sri.com/users/tiwari/relational-abstraction/) (GPL-2, LISP): creating relational abstractions of HybridSAL models (SRI)
    * `hsal2xml` (GPL-2, Java): `HybridSAL` -> `XML`
- [NLToolbox](http://www-verimag.imag.fr/~tdang/NLTOOLBOX/) (u, C/C++): Non-linear dynamical system reachability: polynomial using Bernstein expansion, more general using hybridization ([VERIMAG](http://www-verimag.imag.fr/~tdang/))
- [Flow*](http://systems.cs.colorado.edu/research/cyberphysical/taylormodels/) (GPL-3, C++): Over-approximation Taylor model flowpipes: polynomial ODEs, polynomial invariants, guards, resets (RWTH Aaachen, Univ. Colorado Boulder)
- [HSolver](http://hsolver.sourceforge.net/) (LGPL): based on RSOLVER constraint solver, correctness does not depend on floating point rounding errors, handles non-linear ODEs ([Academy of Sciences Czech Republic](http://www2.cs.cas.cz/~ratschan/))
- [AMC](http://symbolaris.com/info/amc.html) (?, Mathematica): model checker for non-linear hybrid systems based on the abstraction refinement framework (CMU, Univ. Oldenburg)
- [pyHybridAnalysis](http://www.dmi.units.it/~casagran/pyHybridAnalysis/) (LGPL-3, Python): ε-semantics reachability ([VERIMAG](http://www-verimag.imag.fr/~dreossi/publications.html), Udine Univ., Trieste Univ.)
- [LtlOpt](http://www.cds.caltech.edu/~ewolff/ltlopt.html) (BSD-3, MATLAB): optimal control of high-dimensional, nonlinear systems using LTL specs ([Caltech](http://www.cds.caltech.edu/~ewolff))
- [reasys](https://github.com/jadecastro/reasyns) (BSD-3, MATLAB): Reactive synthesis for nonlinear systems ([Cornell, Toyota](http://jadecastro.github.io/))
- [c2e2](https://publish.illinois.edu/c2e2-tool/) (?, Assembly): tool for verifying bounded-time invariant properties of Stateflow models (UIUC)
- [HyST](http://verivital.com/hyst/) (LGPLv3, Java / Python / Matlab): transformation and semantics-preserving translation (to Flow*, dReach, HyComp, HyCreate) of hybrid automata networks from SpaceEx format ([AFRL](http://stanleybak.com/), [IST](http://www.sergiybogomolov.com/), [UTA](http://www.taylortjohnson.com/))

## Stochastic
- [MoToR](http://depend.cs.uni-sb.de) (GPL, ?): Macro-preprocessor for MoDeST, a stochastic real-time systems formalism, interfacing to UPPAAL, CADP, Eclipse, Mobius (Univ. Saarlandes)
    * [Eclipse plugin](http://depend.cs.uni-sb.de/index.php?446) (Univ. Saarlandes)
- [MRMC](http://www.mrmc-tool.org/trac/) (GPL-3, C): MC for: Discrete/Continuous Markov Chains, Reward models, decision processes (Univ. Twente, RWTH Aachen)
- [PASS](http://depend.cs.uni-sb.de/tools/pass/) (bin, ?): CEGAR MC for infinite-state probabilistic models, MDPs (Saarland Univ.)
- [INFAMY](http://depend.cs.uni-sb.de/tools/infamy/) (bin, ?): CSL Model Checker for infinite-state Markov chains - CTMCs (Saarland Univ.)
- [PARAM](http://depend.cs.uni-sb.de/tools/param/) (GPL-3, C++): Reachability probability computation for parametric Markov chains - DTMCs (Saarland Univ.)

# Theorem Provers
- [TLAPS](http://tla.msr-inria.inria.fr/tlaps/content/Home.html) (BSD-2, OCaml/C/Perl): Theorem prover for TLA+ using: Isabelle, Zenon, Z3 (INRIA/MSR)
    - [TLAPM v2](https://github.com/tlaplus/v2-tlapm) (BSD-3, OCaml): TLAPS proof manager >= v2 (INRIA/MSR)
    - [TLAPM v1](https://github.com/cartazio/tlaps) (BSD-2, OCaml): TLAPS proof manager < v2 (INRIA/MSR)
    - [`pf2`](https://research.microsoft.com/en-us/um/people/lamport/latex/latex.html) (LaTeX): package for writing structured proofs of the form described in ["How to write a 21st century proof"](https://research.microsoft.com/en-us/um/people/lamport/pubs/proof.pdf)
    - [`pfnum`](https://research.microsoft.com/en-us/um/people/lamport/latex/pfnum.html) (C): Rewrites structured proofs in a LaTeX file to renumber proofs steps as they will appear after typesetting
    - [`pf2html`](https://sourceforge.net/projects/pf2html/) [home](http://www.dbai.tuwien.ac.at/proj/pf2html/index.html) (GPL-2, Perl): adds functionality to LATEX2HTML such that LATEX documents written with pf.sty can be viewed in a web browser up to the desired level of detail for each branch of a structured proof (TU Wien)
    - [`hyperpf`](https://research.microsoft.com/en-us/um/people/lamport/proofs/hyperpf.html) (C): HyperTeXt structured proof reader
    - [Verifying TLA+ invariants using ACL2](http://people.csail.mit.edu/cpacheco/publications/verifying-tla-abstract.html) (UT Austin)
- [Isabelle](http://www.cl.cam.ac.uk/research/hvg/Isabelle/) [github](https://github.com/seL4/isabelle) (BSD-3, ML): (Univ. Cabridge, TU Munchen, Univ. Paris-Sud)
    * [Isabelle/TLA](http://homepages.loria.fr/SMerz/projects/isabelle-tla/) [github](https://github.com/seL4/isabelle/tree/master/src/HOL/TLA): encoding of Lamport's TLA in Isabelle, ships with Isabelle's standard distribution ([INRIA](https://members.loria.fr/SMerz/index.html))
    * [APL](https://www.isa-afp.org/): Archive of Formal Proofs
- [HOL](https://hol-theorem-prover.org) (BSD-3, ML): Interative Theorem proving in higher-order logic ([Univ. Cambridge](http://www.cl.cam.ac.uk/research/hvg/HOL/))
    * [Holfoot](http://holfoot.heap-of-problems.org/) (BSD, [ML](https://github.com/HOL-Theorem-Prover/HOL/tree/develop/examples/separationLogic/src)): Implementation of Smallfoot inside of HOL 4
    * [HOLBDDlib](http://www.cl.cam.ac.uk/~mjcg/HolBddLib/) (BSD-3, [ML](https://github.com/HOL-Theorem-Prover/HOL/tree/develop/examples/HolBdd)): kernel of representation judgement rules as infrastructure for building fully-expansive combinations of HOL theorem proving and BDD-based symbolic calculation algorithms, uses the BuDDy BDD package
- [HOL Light] (https://www.cl.cam.ac.uk/~jrh13/hol-light/) (BSD-2, [OCaml](https://github.com/jrh13/hol-light)): Interactive Theorem Proving in higher-order logic (Cambridge Univ., AWS)
- [HOL Zero](http://www.proof-technologies.com/holzero/index.html) (BSD, OCaml): Basic theorem prover for the HOL logic for checking and/or consolidating proofs created on other theorem provers, and a pedagogical example
    * [HOL Zero](https://github.com/domasin/NHolZ/) (BSD, F#): port to F#
- [HOL-Omega](http://trustworthytools.com/id17.html) (BSD-3, [ML](https://github.com/HOL-Theorem-Prover/HOL/tree/HOL-Omega): Merging of HOL4, HOL2P by Völker, and major aspects of System Fω from chapter 30 of Types and Programming Languages by Pierce, implements a new logic, which is an extension of the existing higher order logic of the HOL4 system
- [Coq](http://coq.inria.fr/) (INRIA, Ecole Polytechnique, Paris-Sud 11 Univ., Paris Diderot Univ., CNRS)
    - [HoTT library](https://github.com/HoTT/HoTT) (BSD-2, Coq): A formalization of homotopy type theory in the Coq proof assistant
    - [UniMath](https://github.com/UniMath/UniMath) (FOSS, Coq): A library that aims to formalize a substantial body of mathematics using the univalent point of view.
    - [TLA^{Coq}](https://github.com/philipjf/AWG-AVOCS-2016) (?, Coq): Deep embedding of TLA in Coq (Univ. of Oregon, Sandia)
    - [Coq-Polyhedra](https://github.com/nhojem/Coq-Polyhedra) (CeCILL-B, Coq): Formalizing convex polyhedra in Coq ([INRIA/École Polytechnique](http://www.cmap.polytechnique.fr/~allamigeon/))
- [PVS](http://pvs.csl.sri.com/), its [github](https://github.com/samowre/PVS.git) (GPL-3, Common LISP/C/Emacs LISP/etc): Specification language & TP, based Church's type theory extended with dependent types (SRI)
    * [NASA PVS Library](https://github.com/nasa/pvslib) (Various, Python/Lisp): Collection of formal PVS developments ([NASA Langley](https://shemesh.larc.nasa.gov/fm/))
    * [Invariant-Checker](http://www-verimag.imag.fr/~graf/INVARIANT-CHECKER/): predicate abstraction and verification of invariance reactive properties using theorem-proving and MC, front to PVS ([IMAG](http://www-verimag.imag.fr/~graf/))
- [Lean](https://github.com/leanprover/) (Apache-2, C++/Python): Theorem prover ([Microsoft Research](http://leodemoura.github.io/))
    - [Spectral](https://github.com/cmu-phil/Spectral) (Apache-2.0, Lean): Formalization of the Serre spectral sequence in Lean 2.
- [Zenon](http://zenon-prover.org/) (BSD-3, OCaml): FOL with equality based on tableau, generates Coq proofs [OPAM](http://opam.ocaml.org/packages/zenon/zenon.0.7.1/) (INRIA)
    * [Zenon arith](https://www.rocq.inria.fr/deducteam/ZenonArith/index.html) (BSD-3, OCaml): extension to handle linear arithmetic (INRIA)
    * [Zenon modulo](https://www.rocq.inria.fr/deducteam/ZenonModulo/index.html) (BSD-3, OCaml): extension to deduction modulo (INRIA)
    * [Super Zenon](http://cedric.cnam.fr/~delahaye/super-zenon/) (?, ?): extension using superdeduction (CEDRIC/CNAM, Siemens IC-MOL)
- [Nunchaku](https://github.com/nunchaku-inria/nunchaku) (BSD-2, OCaml): A counter-example finder for higher-order logic, designed to be used from various proof assistants (INRIA)
- [Nitpick](https://github.com/seL4/isabelle/blob/e3f58c3db416e00ee7e4280c8c50522b222d7c5e/src/HOL/Nitpick.thy) (BSD-3, Isabelle): Counterexample generator for Isabelle/HOL
- [Walnut](https://github.com/hamoonmousavi/Walnut) (GPLv3, Java): Automated Theorem Prover for Automatic Words
- [Phox](https://raffalli.eu/phox/) (LGPL-3.0, [OCaml](https://github.com/craff/phox)): Proof assistant based on High Order logic which is eXtensible (Université de Savoie)
- [Dedukti](https://deducteam.github.io) (CecILL-B, [OCaml](https://github.com/Deducteam/Dedukti)): Implementation of the λΠ-calculus modulo rewriting
    * [Dedukti libraries](https://github.com/Deducteam/Libraries) (?, Dedukti): A collection of hand-written files for Dedukti
- [Automath](https://en.wikipedia.org/wiki/Automath) (?, ?): One of the first formal proof languages and proof checker ([Eindhoven Univ.](https://en.wikipedia.org/wiki/Nicolaas_Govert_de_Bruijn))
    * [Modern Automath implementation](http://www.cs.ru.nl/~freek/aut/) (?, C): Languages AUT-68, AUT-QE ([Radboud Univ. Nijmegen](http://www.cs.ru.nl/~freek/index.html))
- [TPS](http://gtps.math.cmu.edu/tps.html): (CMU)
- [ALF](http://www.cse.chalmers.se/research/group/logic/alf/guide.html) (Univ. Goterborg/Chalmers)
- [Alfa](http://www.cse.chalmers.se/~hallgren/Alfa/): successor of ALF
- [Agda](http://wiki.portal.chalmers.se/agda/pmwiki.php) (MIT and BSD-2, [Haskell](https://github.com/agda/agda/)): An interactive system for writing and checking proofs, based on intuitionistic type theory. A dependently typed functional programming language.
    - [HoTT-Agda](https://github.com/HoTT/HoTT-Agda) (MIT, Agda): A library of homotopy type theory and univalent foundations
- [Cedille](https://cedille.github.io/) (MIT, Agda/Haskell):
    interactive theorem-prover and dependently typed programming language,
    based on extrinsic (aka Curry-style) type theory
- [ACL2](http://www.cs.utexas.edu/users/moore/acl2/) (BSD-3, [Lisp](https://github.com/acl2/acl2)):  logic and programming language in which you can model computer systems, together with a tool to help you prove properties of those models. "ACL2" denotes "A Computational Logic for Applicative Common Lisp", part of Boyer-Moore family of provers (Univ. Texas at Austin)
    * [Nqthm](http://en.wikipedia.org/wiki/Nqthm) (GPL-2, ?): Boyer–Moore TP using Pure LISP variant, precursor to ACL2 (Univ. Texas, Austin)
    * [Milawa](http://www.cs.utexas.edu/users/moore/acl2/manuals/current/manual/index-seo.php/ACL2____MILAWA?path=3524/3584/475) (MIT, [Lisp](https://github.com/acl2/acl2/tree/master/books/projects/milawa)): "Self-verifying" theorem prover for an ACL2-like logic (UT Austin)
    * [Jitawa](https://www.cl.cam.ac.uk/~mom22/jitawa/) (?, Lisp): Verified Lisp runtime that hosts Milawa and ensures its soundness, as formally proved (Cambridge Univ.)
    * [ivy](https://www.cs.unm.edu/~mccune/papers/ivy/) (BSD-3, [Lisp](https://github.com/acl2/acl2/tree/master/books/workshops/1999/ivy)): Preprocessor and proof checker for resolution/paramodulation theorem provers, coded in ACL2 and proved sound for finite interpretations ([Univ. of New Mexico](https://www.cs.unm.edu/~mccune/))
- [INKA5](http://www.dfki.de/vse/systems/inka/inka5.html), [INKA](http://www.dfki.de/vse/systems/inka/): Inductive Theorem Prover
- [Otter & Mace2](http://www.cs.unm.edu/~mccune/otter/): first-order and equational logic
- [Prover9 & Mace4](http://www.cs.unm.edu/~mccune/prover9/): Successors of Otter & Mace2
- [EQP](http://www.cs.unm.edu/~mccune/eqp/): first-order equational logic: associative-commutative unification and matching, a variety of strategies for equational reasoning, and fast search
- [TWELF](http://twelf.org/wiki/Main_Page)
- [Maude ITP](http://maude.cs.uiuc.edu/tools/itp/): Inductive Theorem Prover
- [Vampire](http://www.vprover.org/) (FUSC, C++): FOL ([Novosibirsk](http://www.voronkov.com/), Univ. Machester, Chalmers UT, Vienna UT)
    * [Drakosha](http://www.vprover.org/authors.cgi) (?, LISP): Vampire's predecessor
- [LP: Larch Prover](http://www.sds.lcs.mit.edu/spd/larch/LP/overview.html) (?): Multisorted first-order logic, interactive (MIT)
    * [Larch Shared Language (LSL) Checker](http://www.sds.lcs.mit.edu/spd/larch/LSL/index.html)
    * [Larch/C++](http://www.eecs.ucf.edu/~leavens/larchc++.html) (?): Interface Specification Language for C++ (Iowa State Univ.)
    * [Larch/Smalltalk](http://www.eecs.ucf.edu/~leavens/larchSmalltalk.html) (?): Behavioral interface specification language for Smalltalk-80 (Iowa State Univ.)
- [SAL](http://sal.csl.sri.com/) (GPL-2, Scheme): Language for specifying concurrent systems in a compositional way. BDD-based & SAT-based MC, experimental "Witness" MC, "infinite" bounded MC based on SMT solving, simulator, deadlock checker, automated test generator (SRI, Stanford, Berkeley)
- [Gappa](http://gappa.gforge.inria.fr/) (GPL-3, CeCILL): for numerical programs dealing with floating-point or fixed-point arithmetic (INRIA)
- [Mizar](http://mizar.org/)
- [NuPRL](http://www.nuprl.org/): Formal Digital Library (Cornell)
- [MetaPRL](http://www.cs.cornell.edu/jyh/metaprl/default.html)
- [Matita](http://matita.cs.unibo.it/index.shtml) (GPLv3, [OCaml](http://matita.cs.unibo.it/gitweb/?p=helm.git;a=summary)): Interactive theorem prover based on calculus of inductive constructions (Univ. of Bologna)
- [Gandalf](http://deepthought.ttu.ee/it/gandalf/)
- [E-SETHEO](http://www4.informatik.tu-muenchen.de/~schulz/WORK/e-setheo.html): strategy-parallel compositional theorem prover for first-order logic with equality
- [SPASS](http://www.spass-prover.org/): First-Order Logic with Equality (Max Planck Inst. Inf.)
- [Omega](https://github.com/theoremprover-museum/OMEGA) (?, Isabelle/Lisp): for higher-order logic based on proof planning
- [Omega](https://code.google.com/p/omega/) (BSD-3): cross between a purely functional programming language and a theorem prover
- [wikipedia list](https://en.wikipedia.org/wiki/Automated_theorem_proving)
- [this thread](http://cs.stackexchange.com/questions/868/types-of-automated-theorem-provers)
- [jImp](http://symbolaris.com/logic/jImp.html) (binary, Java): based on set of support and ordered resolution for first-order logic, supports: clause indexing techniques, subsumption, and tautology elimination, Davis-Putnam-Loveland-Logemann (DPLL) inference procedure (CMU)
- [QEPCAD](http://www.usna.edu/CS/~qepcad/B/QEPCAD.html) and [github](https://github.com/PetterS/qepcad) (BSD-like, C): Quantifier elimination by partial cylindrical algebraic decomposition (US Naval Academy, Drexel Univ., North Carolina State Univ.)
    * [Mac OS X 10.6, 10.7 binaries](http://www.cl.cam.ac.uk/~lp15/papers/Arith/qepcad-for-mac.html) (Cambridge Univ.)
- [E](http://www4.informatik.tu-muenchen.de/~schulz/E/E.html) (GPL-2, C): Full first-order logic with equality ([TU Munchen](http://www4.in.tum.de/~schulz/Stephan_Schulz/Stephan_Schulz.html))
- [Community Z Tools](http://czt.sourceforge.net/) (GPL-2, Java): Tools for editing, typechecking and animating Z specifications and related notations, including Java framework for building formal methods tools (Univ. Oxford, contrib)
- [ProofPower](http://www.lemma-one.com/ProofPower/index/) (GPL, ?): Tool suite supporting specification and proof in HOL and Z notation (Lemma 1 Ltd)
- [ClawZ](http://www.lemma-one.com/clawz_docs/clawz_docs.html) (?, ?): Simulink -> Z notation (Lemma 1 Ltd)
- [Waldmesiter](http://www.waldmeister.org/index.htm) (FUSC, ?): TP for unit equational logic (Max Planck Inst. Informatik)
- [Spear](http://www.domagoj-babic.com/index.php/ResearchProjects/Spear)
- [Metamath](http://us.metamath.org): Tiny language based on ZFC, and also database of proved theorems
- [Theorema](https://github.com/windsteiger/Theorema) (GPLv3, Mathematica): a system for automated reasoning (theorem proving) and automated theory exploration based on Mathematica ([JKU](http://www.risc.jku.at/research/theorema/software/))
- [Princess](http://www.philipp.ruemmer.org/princess.shtml) (GPL-3, Scala): FOL modulo linear integer arithmetic
    * [Seneschal](http://www.philipp.ruemmer.org/seneschal.shtml) (GPL-3, Java): synthesising linear ranking functions for programs expressible in Presburger arithmetic
- [FOL prover](https://github.com/boyers/theorem_prover) (BSD, Python): automated theorem prover for first-order logic, guaranteed to prove any provable formula ([MIT](http://www.stephanboyer.com/))
- [hemera](https://github.com/arademaker/hemera) (?, Python): yet another simple theorem prover (PUC-Rio)
- [FLiP](https://github.com/jon-jacky/FLiP) (GPL, Python): Library for defining logics and writing theorem prover applications, e.g., a proof checker for natural deduction proofs ([Univ. Wasignton](http://staff.washington.edu/jon/))
- [ATS](http://www.ats-lang.org/) (GPL-3, C): A statically typed multiparadigm programming language that unifies implementation with formal specification, using theorem proving (Boston Univ.)
- [F*](https://www.fstar-lang.org/) (Apache 2.0, [OCaml, F\#](https://github.com/FStarLang/FStar)): ML-like functional programming language aimed at program verification. Its type system includes polymorphism, dependent types, monadic effects, refinement types, and a weakest precondition calculus (MSR, INRIA)
- [`proofcheck`](http://www.proofcheck.org/) (GPL, Python): Checks mathematical proofs written in La/TeX, attempts to handle mathematical language formalized according to the author's preferences as much as possible ([PyPI](https://pypi.python.org/pypi/proofcheck/1.0)) ([Widener Univ.](http://cs.widener.edu/~neveln/))
- [ProofPeer](http://www.proofpeer.net/) (MIT, [Scala/Isabelle](https://github.com/proofpeer)): Collaborative theorem proving ([Edinburgh Univ.](http://www.proofpeer.net/contact.html))
- [Nitpick](http://www.cs.cmu.edu/afs/cs.cmu.edu/project/nitpick/www/home.html) (?): Checker for Z specifications (CMU)
- [Globular](http://globular.science) (WTFPL, [JavaScript](https://github.com/jamievicary/globular)): An online proof assistant for hiher-dimensional rewriting, produces graphical visualizations of higher-dimensional proofs, used for category theory proofs
- [Abella](http://abella-prover.org) (GPLv3, [OCaml](https://github.com/abella-prover/abella)): Interactive theorem prover based on lambda-tree syntax, well-suited for reasoning about the meta-theory of programming languages and other logical systems that manipulate objects with binding ([Univ. of Minnesota](http://www-users.cs.umn.edu/~gopalan/), [LIX/École polytechnique](https://www.lix.polytechnique.fr/), [INRIA/Saclay](https://www.inria.fr/en/centre/saclay))
- [GAPT](https://github.com/gapt) (GPLv3, Scala): Framework for transforming and processing proofs, and interfaces to automated reasoning tools (provers, SMT solvers, SAT solvers)
- [homotopy.io](https://homotopy.io) (CC BY-NC 3.0, [JavaScript](https://github.com/homotopy-io/homotopy-webclient)): A proof assistant for n-categories
- [Andromeda](http://www.andromeda-prover.org/) (BSD-2, [OCaml](https://github.com/Andromedans/andromeda)): A proof assistant for general type theories, LCF-style, with statically typed meta-language Andromeda ML
- [Alg](https://github.com/andrejbauer/alg) (BSD-2, OCaml): A program that generates all finite models of a first-order theory. It is optimized for equational theories.
- [RZ](https://github.com/andrejbauer/rz) (MIT, OCaml): A tool for automatic generation of specifications based on realizability theory
- [LEGO](http://www.dcs.ed.ac.uk/home/lego/) (?, [ML](https://github.com/theoremprover-museum/LEGO)): an interactive proof development system (proof assistant), implementing various related type systems: the Edinburgh Logical Framework (LF), the Calculus of Constructions (CC), the Generalized Calculus of Constructions (GCC) and the Unified Theory of Dependent Types (UTT) (Univ. of Edinburgh)
- [IMPS](https://github.com/theoremprover-museum/imps) (MITRE, Perl/Lisp): Intended to provide mechanical support for traditional mathematical techniques and styles of practice, with underlying logic simple type theory (MITRE)
- [Museum of theorem provers](https://theoremprover-museum.github.io): front-end to a collection of source code repositories for theorem provers, hosted on GitHub

## Theorem provers for modal logics

- [ls4](https://github.com/quickbeam123/ls4) (MIT, C++, C): PLTL prover based on labelled superposition with partial model guidance, with MiniSAT behind, and used as backend by TLAPS ([Univ. Manchester](http://forsyte.at/people/suda/))
- [T2](http://mmjb.github.io/T2/) (F\#, Mono, MIT): Prover of CTL\* of programs, with `z3` behind (replaces TERMINATOR) ([MSR](http://research.microsoft.com/en-us/people/mabrocks/), [UCL](http://heidyk.com/))
- [TRP++](http://cgi.csc.liv.ac.uk/~konev/software/trp++/) [files](http://cgi.csc.liv.ac.uk/~konev/software/trp++/translator/) (GPL-2, C++): theorem prover for PLTL based on the temporal resolution calculus ([Univ. Liverpool](https://cgi.csc.liv.ac.uk/~konev/))
    - [TRP](http://cgi.csc.liv.ac.uk/~ullrich/TRP/) (?, Prolog): earlier implementation of TRP++
- [LWB](http://www.lwb.unibe.ch) (?, C++): The Logics Workbench, online prover for classical and non-classical propositional logics, including nonmonotonic apporaches (logics: CPC, IPC, K, KT, S4, S5, q, KN, KTn, S4n, PLTL, TK, LL, AEL) (Univ. Berne)
- [TRS](http://www.sc.ehu.es/jiwnagom/paginaMarisa_archivos/TRS.html) (?, ?): Resolution-based theorem prover for PLTL, [online interface](http://trs-tool.appspot.com/) only (UBC)
- [TLPVS](http://www.cs.nyu.edu/acsys/tlpvs/tlpvs.html): PVS implementation of an LTL verification system (NYU)
- [STeP](http://www-step.stanford.edu/): Stanford temporal prover
- [CTLSAT](https://github.com/nicolaprezza/CTLSAT) (?, C++): CTL satisfiability solver
- [MLSolver](https://github.com/tcsprojects/mlsolver) (?, Ocaml): Solver for satisfiability and validity of modal fixpoint logics (Univ. Munich, Univ. Kassel)
- [Leviathan](https://github.com/Corralx/leviathan) (BSD-3, C++): Tableau prover for LTL satisfiability (Univ. Udine)
- [PLTLProvers](http://users.cecs.anu.edu.au/~rpg/PLTLProvers/): (?, OCaml): 3 PLTL theorem prover variants
- [LoTREC](https://www.irit.fr/Lotrec/) (FSLA): Generic tableau prover
- [MleanTAP](http://www.leancop.de/mleantap/) (?, Prolog): Sound and complete theorem prover based on free-variable semantic tableaux extended by an additional prefix unification (logics: D, T, S4, S5) (TU Darmstadt)
- [List of tools for modal logics](http://www.cs.man.ac.uk/~schmidt/tools/) (Univ. Manchester)
- [Schuppan-Darmawan](http://www.schuppan.de/viktor/atva11/) benchmark results of LTL satisfiability solvers
- [TPTP](http://www.cs.miami.edu/~tptp/): Problem library for automated theorem proving (Univ. Miami)
- [QMLTP](http://www.iltp.de/qmltp/systems.html): Benchmarking results for theorem provers for first-order modal logics

## QBF
- [QBF Solvers](http://www.cs.toronto.edu/~fbacchus/qbf.html#PreQuel) (C++)
- [RAReQS](http://sat.inesc-id.pt/~mikolas/sw/areqs/) (GPL, C++/uses MiniSAT): Recursive abstraction refinement QBF solver ([INESC-ID Lisboa](http://sat.inesc-id.pt/~mikolas/))
- [Quantor](http://fmv.jku.at/quantor/) (BSD): QDIMACS input (JKU)
- [DepQBF](http://lonsing.github.io/depqbf/) (GPL, C): search-based ([TU Wien](http://www.kr.tuwien.ac.at/staff/lonsing/), JKU)
- [nenofex](https://github.com/lonsing/nenofex) (GPL, C): expansion-based for NNF ([TU Wien](http://www.kr.tuwien.ac.at/staff/lonsing/), JKU)
- [CAQE](https://www.react.uni-saarland.de/tools/caqe/) (Apache-2, C): certifying solver based on CEGAR-based clausal abstraction (Saarland Univ., UC Berkeley)
- [QBFLIB](http://vlsicad.eecs.umich.edu/BK/Slots/cache/www.qbflib.org/): Collection of benchmark problems, solvers, and tools related to Quantified Boolean Formula (QBF) satisfiability (Univ. Michigan)

## SAT
- [SAT Live](http://www.satlive.org/): news outlet

### CDCL

- [MiniSat](http://minisat.se/) and its [github](https://github.com/niklasso/minisat) (MIT, C++/C): minimalistic high-performance solver to help get started ([Chalmers Univ.](http://minisat.se/Authors.html))
    * [`simplesat`](https://github.com/enthought/sat-solver) (BSD-3, Python): Python implementation based on MiniSat, for handling package dependencies
    * [ruby-minisat](https://github.com/mame/ruby-minisat) (MIT, Ruby): bindings
    * [qmaxsat](https://sites.google.com/site/qmaxsat/) (MIT, C/C++): Q-dai MaxSAT Solver, based on MiniSat
    * [MiniMarch](http://www.st.ewi.tudelft.nl/sat/minimarch.php)
    * [Glucose](http://www.labri.fr/perso/lsimon/glucose/): CDCL with new scoring scheme for clause learning (CRIL)
    * [MiniSAT+](https://github.com/niklasso/minisatp)
- [Lingeling, Plingeling, Treengeling](http://fmv.jku.at/lingeling/)
- [PicoSAT](http://fmv.jku.at/picosat/) (MIT, C)
    * [Python bindings](https://pypi.python.org/pypi/pycosat) (MIT, Python)
    * [`pigosat`](https://github.com/wkschwartz/pigosat) (BSD, Go): bindings
- [Sat4j](http://www.sat4j.org/) (EPL or LGPL, Java): SAT, MAXSAT, Pseudo-Boolean, MUS (Artois Univ., CNRS, CRIL)

### Stochastic local search
- [UBCSAT](http://www.satlib.org/ubcsat/): (Univ. British Columbia)

### Parallel
- [PeneLoPe](http://www.cril.univ-artois.fr//~hoessen/penelope.html) (BSD-like C++) (CRIL)
- [CombiSAT](https://github.com/stefanbucur/CombiSAT) (?, Python): Portfolio solver running multiple sequential solvers with different strategies ([EPFL](http://people.epfl.ch/stefan.bucur))
- [PWBO](http://sat.inesc-id.pt/pwbo/)

### Unsorted
- [zChaff](http://www.princeton.edu/~chaff/zchaff.html) (Princeton Open Source): Chaff algorithm ([Princeton](http://www.princeton.edu/~chaff/))
- [SATABS](http://www.cprover.org/satabs/) (BSD, C): ANSI-C, C++ verification via Boolean program abstraction (Univ. Oxford, Imperial College, Univ. Lugano, CMU)
- [NanoSAT](http://fmv.jku.at/nanosat/) (BSD): (JKU)
- [Boppo](http://www.cprover.org/boppo/) (?): MC for Boolean programs featuring: POR, Fixpoint detection using QBF, support for `constraint` construct (Univ. Oxford, Microsoft Research, Univ. Lugano, CMU)
- [CSIsat](http://www.sosy-lab.org/~dbeyer/CSIsat/) (Apache): Interpolating decision procedure for the quantifier-free theory of rational linear arithmetic and equality with uninterpreted function symbols (EPFL, SFU)
- [MSUnCore](http://logos.ucd.ie/wiki/doku.php?id=msuncore): solving (Weighted) (Partial) Maximum Satisfiability (MaxSAT)
- [antom](https://projects.informatik.uni-freiburg.de/projects/antom) (C++): Lib solving: SAT, Unweighted MaxSAT, Partial MaxSAT, \#SAT (Uni. Freiburg)
- [SCIP](http://scip.zib.de/): Mixed int programming (MIP), constraint int programming and branch-cut-and-price
    * [scip-maxsat](https://github.com/msakai/scip-maxsat) (ZIB, C++): Max-SAT frontend for SCIP
- [GLPK](http://www.gnu.org/software/glpk/)
    * [MaxSAT frontend](https://github.com/msakai/glpk-maxsat) for GLPK
- [PrecoSAT](http://fmv.jku.at/precosat/) (MIT-like)
- [RSat](http://reasoning.cs.ucla.edu/rsat/home.html)
- [fss](http://dudka.cz/fss) (GPL-3, C++/GAlib): Genetic algorithms
- [MiFuMaX](http://sat.inesc-id.pt/~mikolas/sw/mifumax/) (GPL-3)
- [Shaowei Cai solvers](http://shaoweicai.net/research.html)
- [algorithms](https://github.com/msakai/toysolverw)
- [WBO](http://sat.inesc-id.pt/wbo/): Weighted Boolean Optimization Solver that extends Weighted-Partial MaxSAT and Pseudo-Boolean Optimization
    * [open-WBO](http://sat.inesc-id.pt/open-wbo/) (MIT, C++): open source version of WBO
- [ToulBar2](https://mulcyber.toulouse.inra.fr/projects/toulbar2/) (GPL, C++): weighted constraint satisfaction solver (INRA)
- [march](http://www.isa.ewi.tudelft.nl/sat/march.htm): DPLL with lookahead heuristics (TU Delft)
- [march_eq](http://www.st.ewi.tudelft.nl/sat/march_eq.htm): (TU Delft)
- [march_dl](http://www.st.ewi.tudelft.nl/sat/march_dl.php): (TU Delft)
- [CryptoMiniSat](http://www.msoos.org/cryptominisat2/), its [github](https://github.com/msoos/cryptominisat) (LGPL, C++, Python)
- [WinSAT](http://www.mqasem.net/sat/winsat/)
- [HyperSAT](http://www.domagoj-babic.com/index.php/ResearchProjects/HyperSAT): Experiment with B-cubing search space pruning
- [Kodkod](http://alloy.mit.edu/kodkod/) (MIT, Java): SAT-based constraint solver for first order logic with relations, transitive closure, bit-vector arithmetic, and partial models, with finite model finder and minimal unsatisfiable core extractor (MIT)
- [Kaplan](http://lara.epfl.ch/w/kaplan) (?, Scala): Scala extension that supports constraint-solving (EPFL)
- [iSAT](https://projects.avacs.org/projects/isat/): DPLL-style solver developed for large Boolean combinations of non-linear arithmetic constraints involving transcendental functions
- [HySAT](http://www.uni-oldenburg.de/hysat/)
- [Scarab](http://kix.istc.kobe-u.ac.jp/~soh/scarab/) (BSD, Scala): SAT-based constraint programming
- [Limboole](http://fmv.jku.at/limboole/) (Unlicense, ?): satisfiability of arbitrary structural formulas, not just CNF
- [MiFuMaX](http://sat.inesc-id.pt/~mikolas/sw/mifumax/)
- [UBCSAT](https://github.com/dtompkins/ubcsat) (FUSC, C): Stochastic local search solver (Univ. British Columbia)
- [QNF2z3](http://sat.inesc-id.pt/~mikolas/sw/qcnf2smt/) (FUSC, Python/Bash): invoking Z3 on QDIMACS instances (INESC Lisboa)
- [ToughSAT](http://toughsat.appspot.com/): generates "difficult" SAT instances
- [minibones](http://sat.inesc-id.pt/~mikolas/sw/minibones/) (FUSC): computing backbone literals
- [SBSAT](http://www.cs.uc.edu/~weaversa/SBSAT.html): state-based  (U Cincinnati)
- [satsolver](https://github.com/stephenroller/satsolver) (?, Python): DPLL implementation for educational purposes
- [Potassco](http://potassco.sourceforge.net/): answer set programming collection: Clasp, Gringo, Clingo, Aspcud, Clingcon, claspfolio, coala solvers
- [miniC2D](http://reasoning.cs.ucla.edu/minic2d/) (?): knowledge compilation and model counting based on exhaustive DPLL (UCLA)
- [toulbar2](http://www7.inra.fr/mia/T/toulbar2/) (GPL, C++): Exact solver for cost function networks (INRIA, Barcelona)


## SMT
- [CVC4](http://cvc4.cs.nyu.edu/web/) (BSD-3, [C++](https://github.com/CVC4/CVC4)): built-in base theories, quantifiers, interactive text-based interface, interfaces to: C/C++, Python, Java, OCaml, PHP, Perl, Ruby, Tcl, model generation, (NYU, Univ. Iowa)
- [CV3](http://www.cs.nyu.edu/acsys/cvc3/) (BSD-3, [C++](https://github.com/msakai/cvc3)): predecessor of CVC4 (Stanford, NYU, Univ. Iowa)
- [Z3](https://github.com/Z3Prover/z3) (MIT, C++/Python): `.smt2`, `.dimacs`, `.cnf`, `.dl`, `.smt` (Microsoft Research)
    * [Z3_Haskell](https://github.com/kayceesrk/Z3_Haskell) (BSD, Haskell): bindings for Z3 (Cambridge Univ.)
    * [`hz3`](https://github.com/tizmd/hz3) (BSD, Haskell): bindings to low-level API for Z3
    * [ScalaZ3](https://github.com/epfl-lara/ScalaZ3/) (Scala): bindings for Z3 (EPFL)
    * [bapa-z3](https://github.com/psuter/bapa-z3) (BSD, Scala): Boolean algebra with Presburger arithmetic constraints plug-in for Z3 (EPFL)
    * [Z3-str](https://github.com/z3str/Z3-str) (MIT, C++/Python): string theory plug-in for Z3 (Purdue)
    * [Z3Fs](https://github.com/dungpa/Z3Fs) (MIT, F\#): DSL for SMT problems using Z3 API in F\#
- [iZ3](http://rise4fun.com/iZ3) ([FUSC](http://z3.codeplex.com/license), C++/Python): Interpolating, supports: arithmetic, arrays, uninterpreted functions, and quantifiers (Microsoft Research)
- [Yices](https://yices.csl.sri.com) (GPLv3, [C](https://github.com/SRI-CSL/yices2)): SMT solver that decides the satisfiability of formulas containing uninterpreted function symbols with equality, real and integer arithmetic, bitvectors, scalar types, and tuples. Supports both linear and nonlinear arithmetic. Reads input from SMT-LIB or Yices' own specification language, includes Python bindings (SRI/CSL)
- [Boolector](http://fmv.jku.at/boolector/) (GPL-3): bit-vectors and arrays (Johannes Kepler Univ. Linz, Upper Austrian Univ. of Applied Sciences)
- [MathSAT](http://mathsat.fbk.eu/download.html) (FUSC, C++, Python/Java bindings): Theories: equality and uninterpreted functions, linear arithmetic, bit-vectors, and arrays, and Functionalities: computation of Craig interpolants, extraction of unsatisfiable cores, generation of models and proofs, and the ability of working incrementally (FBK, Univ. Trento)
- [SMT-LIB](http://www.cprover.org/SMT-LIB-LSM/) (?, C++): format for Finite lists, sets, maps (Oxford Univ.)
- [Alt-ERGO](http://alt-ergo.lri.fr/) (FUSC, [OCaml](https://github.com/OCamlPro/alt-ergo)): built upon CC(X) algorithm (INRIA, Univ. Paris Sud, CNRS, Lri)
- [mSAT](https://gbury.github.io/mSAT/) (Apache-2.0, [OCaml](https://github.com/Gbury/mSAT)): Modular SAT/SMT solver with proof output, derives from ERGO (INRIA)
- [veriT](http://www.verit-solver.org/) (BSD-2, C/C++): Complete for quantifier-free formulas with uninterpreted functions and difference logic on real numbers and integers (INRIA, Nancy Univ., UFRN, CNPq, Loria)
    * [haRVey](http://harvey.loria.fr/) (LGPL/BSD-2, C/C++): Predecessor of veriT: haRVey-FOL (LGPL), haRVey-SAT (BSD-2) (INRIA, Nancy Univ., UFRN, CNPq, Loria)
- [Simplify](http://kindsoftware.com/products/opensource/Simplify/), its [github](https://github.com/kiniry/Simplify) (?, Modula-III): (SRC)
- [Beaver](http://uclid.eecs.berkeley.edu/jha/beaver-dist/beaver.html) (BSD, OCaml): for the theory of quantifier-free finite-precision bit-vector arithmetic (UC Berkeley)
- [SBV](https://github.com/LeventErkok/sbv) (BSD-3, Haskell): SMT based verification in Haskell: Express properties about Haskell programs and automatically prove them using SMT solvers (ABC, Boolector, CVC4, MathSAT, Yices, Z3). ([Intel](http://leventerkok.github.io/))
- [list of SMT solvers](http://smtlib.cs.uiowa.edu/solvers.shtml) (Univ. Iowa)

## Other solvers
- [RSolver]() (LGPL): Quantified inequality constraints ([Academy of Sciences Czech Republic](http://www2.cs.cas.cz/~ratschan/))
- [ROSETTE](http://people.csail.mit.edu/emina/pubs/rosette.onward13.pdf): Framework for designing solver-aided languages, realized embedded in [Racket](http://racket-lang.org/) ([UC Berkeley, MIT](http://people.csail.mit.edu/emina/))

## Logic programming
- [miniKanren](http://minikanren.org/)
- [logpy](https://github.com/logpy/logpy)

# Software Synthesis
- [Leon](http://lara.epfl.ch/w/leon), its [github](https://github.com/epfl-lara/leon) (BSD-2, Scala): Automated system for synthesizing and verifying functional Scala programs (EPFL)
- [AutoBayes](http://ti.arc.nasa.gov/opensource/projects/autobayes/) (NOSA, Prolog): automatic generation of customized algorithms from compact, declarative specifications in the data analysis domain, requires SWI Prolog, generates OCtave/Matlab code (NASA)

# Runtime Verification
- [MOP](http://fsl.cs.illinois.edu/index.php/MOP) (Java): Monitoring-Oriented Programming ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
- [CHIMP](http://www.cs.rice.edu/CS/Verification/Software/software.html): LTL -> monitors: nondeterministic finite-word automata that accept all illegal executions (Rice Univ.)
- [LTL_3](http://ltl3tools.sourceforge.net/) (GPL): LTL -> Moore FSM monitor
- [TOPL](http://rgrig.github.io/topl/) (OCaml): monitor Java programs
- [Breach Toolbox](https://github.com/decyphir/breach)(BSD-3, MATLAB/C++): Simulation-based design of dynamical, cyber-physical, and hybrid systems (UC Berkeley, [Decyphir](http://www.decyphir.com/))
- [JTorX](https://fmt.ewi.utwente.nl/redmine/projects/jtorx/wiki/) (?, Java): Model-based testing: Spec: Aldebaran | GraphML | dot | Jararaca | `.sax` | muCRL | `.bcg` | LOTOS, Implementation either these or real program (Univ. Twente)
- [TorX](http://fmt.cs.utwente.nl/tools/torx/introduction.html) (Apache, ?): Conformance testing of reactive software (Univ. Twente, TU Eindhoven, Philips, Lucent)
- [MonPoly] (http://sourceforge.net/projects/monpoly/) (?, OCaml): a prototype monitoring tool that checks compliance of log files with respect to policies specified in MFOTL (Metric First-Order Temporal Logic)
- [Montre](https://github.com/doganulus/montre) (GPL-3, [Pure](http://purelang.bitbucket.org/)/C++): A timed regular expression matcher ([Verimag](http://doganulus.com))

# Yet un-categorized
- [Maude](http://maude.cs.uiuc.edu/overview.html) (UIUC)
    * [C-Reducer](http://sysma.lab.imtlucca.it/tools/c-reducer/): Automatic c-reduction of object based modules for the Maude system (IMT Lucca)
    * [MESSI](http://sysma.lab.imtlucca.it/tools/ensembles/): Design, validation and performance evaluation of self-assembly strategies with Maude (IMT Lucca)
    * [Circ](http://fsl.cs.illinois.edu/index.php/Circ):  automated behavioral prover based on the circularity principle for Maude ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
    * [LTLR](http://maude.cs.uiuc.edu/tools/tlr/): LTL rewriting model checker within Maude (UIUC)
- [Matching Logic](http://www.matching-logic.org/index.php/Matching_Logic): regard a language through both operational and axiomatic lenses at the same time ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
- [Separation logic & local reasoning](https://wiki.mpi-sws.org/star/ToolSupport): wiki & tools list [Max Planck Inst. for Soft. Sys.](http://www.mpi-sws.org/~viktor/)
- [QMRes](http://www.cs.rice.edu/CS/Verification/Software/software.html): Multi-resolution with ZDDs implementation
- [MTSA](http://sourceforge.net/projects/mtsa/) (Public): Modal Transition Systems Analyser (Imperial College London, Univ. Buenos Aires)
- [FoCs](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.23.9941)
- [COMPASS](http://compass.informatik.rwth-aachen.de/): correctness, modeling and preformance of aerospace systems
- [VeriSoft](http://cm.bell-labs.com/who/god/verisoft/): systematic software testing (Bell Labs)
- [FTS](https://projects.info.unamur.be/fts/): featured transition systems
- [PdTrav](http://fmgroup.polito.it/index.php/download/viewcategory/3-pdtrav-package)
- [seL4](https://github.com/seL4/seL4): A microkernel formally proved correct

# TypeSetting
- [LTL](https://github.com/malteschmitz/ltl) (LPPL, LaTeX/TikZ): Configurable LTL math operators with LaTeX and TikZ or LTLFonts
- [fsmtex](https://github.com/benob/fsmtex) (?, Perl/TeX): FSM drawing in LaTeX using TikZ ([Univ. Marseille](pageperso.lif.univ-mrs.fr/~benoit.favre))

# Other tool lists
- [Wikipedia](https://en.wikipedia.org/wiki/List_of_model_checking_tools)
- [Yahoda](http://anna.fi.muni.cz/yahoda/) [Masaryk Univ.]
- [wikia](http://formalmethods.wikia.com/wiki/VL) (by Jonathan Bowen)
- [formal methods wiki](http://web.archive.org/web/20070706205223/http://vl.fmnet.info/) (older version of the above)
- [UPenn Hybrid System Tools Repository](http://wiki.grasp.upenn.edu/hst/index.php?n=Main.HomePage)
- [VERIMAG Tools](http://www-verimag.imag.fr/Tools,12.html?lang=)
- [verification tools for industrial automation](http://www.chihhongcheng.info/tools)
- [Carloni et al.](http://www.nowpublishers.com/articles/foundations-and-trends-in-electronic-design-automation/EDA-001)
- [Networked Control Systems Repository](http://filer.case.edu/org/ncs/)
- [rise4fun](http://rise4fun.com/)
- [CMU tools](http://www.cs.cmu.edu/~modelcheck/code.htm)
- [SRI tools](http://fm-wiki.csl.sri.com/index.php/Main_Page) and older [page](http://fm.csl.sri.com/)
- [SYNALP](http://www.inrialpes.fr/synalp/): SYNchronous Applications, Languages, and Programs
- [ARS](http://www-formal.stanford.edu/clt/ARS/): Database of Automated Reasoning Systems ([Stanford](http://blackforest.stanford.edu/clt/))
- [AVACS](http://www.avacs.org/tools/)
- [Quasimodo](http://www.quasimodo.aau.dk/tools.html): Quantitative system properties in model-driven-design of embedded systems
- [Tools list at SMT-LIB](http://smtlib.cs.uiowa.edu/utilities.html)
- [Max-SAT 2013 solvers](http://maxsat.ia.udl.cat:81/13/solvers/index.html)
- [SAT competition](http://www.satcompetition.org/)
- [JKU tools](http://fmv.jku.at/software/index.html)
- [Freek Wiedijk](http://www.cs.ru.nl/~freek/digimath/bycategory.html#tacticprover)
- [Proof Assistants, Wikipedia](https://en.wikipedia.org/wiki/Proof_assistant)
- [Univ. Utah tools](http://www.cs.utah.edu/formal_verification/hevea-index.html#htoc2)
- [SV-COMP 2014](http://sv-comp.sosy-lab.org/2014/participants.php): competition on software verification at TACAS 2014
- [Every Proof Assistant Seminar](http://math.andrej.com/2020/04/28/every-theorem-prover/): series of (online) seminars

# databases and benchmarks
- [VLTS](http://cadp.inria.fr/resources/vlts/): MC benchmarks (CWI/SEN2, INRIA/VASY)
- [BEEM](http://anna.fi.muni.cz/models/): MC benchmarks ([Masaryk Univ.](http://anna.fi.muni.cz/))
- [Mutual Exclusion Promela Source Codes](http://www.ueda.info.waseda.ac.jp/~kobayashi/Promela/benchmark/index.html): (Waseda Univ.)
- [Buchi Store](http://buchi.im.ntu.edu.tw/index.php/home/index/)
- [Promela Database](http://www.albertolluch.com/research/promelamodels): (IMT Lucca)
- [Spec Patterns](http://patterns.projects.cis.ksu.edu/): patterns commonly occuring in specs of concurrent/reactive systems (LTL, CTL, GIL, QRE, ACTL, RAFMC) (Univ. Massachusetts Amherst)
- [Hybrid system safety verification benchmarks](http://hsolver.sourceforge.net/benchmarks/)
- [TPTP](http://www.cs.miami.edu/~tptp/): Thousands of Problems for Theorem Provers (Univ. Miami)
- [Benchmark Verification Tasks](http://sv-comp.sosy-lab.org/2013/benchmarks.php): Benchmark verification tasks in software verification, as used in SV-COMP
- [Larry Wos' Notebooks](http://www.automatedreasoning.net/): series of notebooks presenting some of Larry Wos’s most recent and hitherto unpublished research in automated reasoning (also in 1st order logic) ([Argon Nat. Lab](https://en.wikipedia.org/wiki/Larry_Wos))
- [SMT-LIB](http://www.smtlib.org/): benchmarks for SMT
- [DPPD](http://users.ecs.soton.ac.uk/mal/systems/dppd.html): The Dozens of Problems for Partial Deduction (DPPD) Library of Benchmarks aims at being a standard suite of benchmarks for partial deduction (Univ. Dusseldorf)
- [QMLTP](http://www.iltp.de/qmltp/): Quantified Modal Logics Theorem Proving (QMLTP) library provides a platform for testing and benchmarking ATP systems for first-order modal logics (Univ. Potsdam)
- [ILTP](http://www.cs.uni-potsdam.de/ti/iltp/): Intuitionistic Logic Theorem Proving (ILTP) library provides a platform for testing and benchmarking ATP systems for first-order and propositional intuitionistic logic (Univ. Potsdam)
- [asparagus](http://asparagus.cs.uni-potsdam.de/): Environment for submitting and archiving benchmarking Answer-Set Programming (ASP) problems and instances (Univ. Potsdam)
- [TPDB](https://www.lri.fr/~marche/tpdb/): Termination Problems Database of test problems for termination provers: term rewrite systems and logic programs (LRI)
- [CSPLib](http://www.csplib.org/): Benchmark library of problems for constraint solvers (Izmir Univ. Economics, Univ. St Andrews, Univ. New South Wales)
- [OR-library](http://people.brunel.ac.uk/~mastjjb/jeb/info.html): Test data sets for a variety of Operations Research (OR) problems (Imperial College London)
- [SATLIB](http://www.satlib.org/): Benchmark problems, solvers, and tools for SAT related research (TU Darmstadt, Univ. British Columbia)
- [SatEx](http://www.swmath.org/software/1588): Experiments and execution traces of SAT solvers, on all benchmarks that are provided

# (non-common) abbreviations
- u: unspecified license
- FUSC: Free Under Specific Condition (wikipedia term), usually free for academic/research use
- closed: no source available, common situation: `jar` files
- LPPL: LaTeX Project Public License
- EPL: Eclipse Public License

- BA: Buchi Automaton
- GBA: Generalized BA
- TP: Theorem Prover
- ATP: Automatic TP

- RTS: Real-time System(s)
- PWA: PieceWise-Affine
- MLD: Mixed Logical Dynamical

- TU: Technical University
- UT: University of Technology
- MSR: Microsoft Research

- FOL: First-order logic
- HOL: Higher-order logic
- bin: binary, no sources available/found
- ?: absent either due to time-constrained browsing (please complete) | not found
