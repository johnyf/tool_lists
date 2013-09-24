List of verification and synthesis tools.
Please clone, contribute and send pull requests.
Minimal markdown knowledge needed to add links:

`- [Tool name](link url) (license, coded in language): brief description (Institution/other maintainer)`

Please list only Open Source/research tools, proprietary ones are not widely and unconditionally useful.
Conditionally (sufficiently) free tools are welcome, e.g., some closed source tools, provided they remain free for educational/research use.

Would you like to suggest a/your tool for addition, but skip cloning/pull requests, please email <jfilippidis@gmail.com>.

To the extent possible under law, the authors have waived all copyright and related or neighboring rights to this text.
You should have received a copy of the CC0 Public Domain Dedication along with this text.
If not, see <https://creativecommons.org/publicdomain/zero/1.0/>.


**Table of Contents**

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Verification](#verification-with-model-checking)
    - [Closed Systems (Everything controlled)](#closed-systems-everything-controlled)
        - [Enumerative](#enumerative)
        - [Symbolic](#symbolic)
    - [logic -> automata and automata tools](#logic-automata-automata-tools)
        - [LTL -> \*BA](#ltl-ba)
        - [LTL -> DRA](#ltl-dra)
        - [other](#other)
    - [Term rewrite systems](#term-rewrite-systems)
    - [Open Systems](#open-systems)
        - [Synchronous Languages](#synchronous-languages)
            - [Imperative](#imperative)
            - [Declarative](#declarative)
            - [Statecharts](#statecharts)
- [Synthesis](#synthesis)
    - [Open Systems (Games: System and Uncontrolled Environment)](#open-systems-games-system-uncontrolled-environment)
        - [Discrete games](#discrete-games)
            - [GR(1) games](#gr1-games)
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



# Verification

## Closed Systems (Everything controlled)

### Enumerative
- [SPIN](https://spinroot.com/spin/whatispin.html) (BSD-3, [C](https://github.com/nimble-code/Spin)): LTL model checking for closed systems in Promela ([JPL/Caltech](https://lars-lab.jpl.nasa.gov/), Bell Labs)
    - [modex](https://spinroot.com/modex/) (FUSC, [C](https://github.com/nimble-code/Modex)): C -> Promela: model extractor ([JPL/Caltech](https://lars-lab.jpl.nasa.gov/), Bell Labs)
    - [`spin`](https://packages.debian.org/buster/spin): Debian Linux package, `apt install spin`
    - [spinja](https://code.google.com/p/spinja/) (Apache-2.0, Java): Promela model checker (Univ. of Twente, TNO)
        - [SpinS](https://fmt.ewi.utwente.nl/redmine/projects/spinja) (Apache-2.0, [Java](https://github.com/utwente-fmt/spins)): an LTSmin language frontend for Promela (Univ. of Twente)
    - [HSF-SPIN](http://www.albertolluch.com/research/tools): SPIN directed model checking extension (IMT Lucca)
    - [Promela Vim Syntax](https://github.com/vim-scripts/promela.vim) (?, VimL): highlighting plugin
    - [Promela Vim Indent](https://github.com/vim-scripts/promela) (?, VimL)
    - [Promela Emacs major mode](https://github.com/emacsmirror/promela-mode) (?, Emacs LISP)
    - [Promela for Sublime Text 3](https://corb.co/projects/sublime-promela-spin) (MIT, [several](https://github.com/corbanmailloux/sublime-promela-spin)): Sublime Text 3 syntax highlighting of Promela
    - [Promela -> NuSMV](https://code.google.com/p/s2n/) (?, C): translator (Peking Univ.)
    - [Promela -> Timed automata with discrete data](https://verics.ipipan.waw.pl/promela): translator, part of Verics
    - [Promela -> C](https://www.ida.liu.se/~kejia/c2promela/) (OCaml): translator (Uppsala Univ.)
    - [Promela -> C](https://www.mathematik.uni-stuttgart.de/~floeff/publications/96-enstparis-s2-report.pdf): translator (Univ. Stuttgart)
    - [Promela -> Java](https://members.tele2.nl/edwin.v/compiler.html) (?, Java): translator ([TU Delft](https://members.tele2.nl/edwin.v/index.html))
    - [LLVM -> Promela](https://github.com/roselone/pmGen) (C++, MIT): LLVM-to-Promela Compiler
    - [jSpin](https://github.com/motib/jspin) ([GPLv2](https://code.google.com/P/Cjspin/), Java): GUI for SPIN and Erigone ([The Weizmann Institute of Science](https://www.weizmann.ac.il/sci-tea/benari/))
    - [Erigone](https://github.com/motib/erigone) ([GPLv2](https://code.google.com/p/erigone/), Ada/Java): partial SPIN re-implementation for educational purposes ([The Weizmann Institute of Science](https://www.weizmann.ac.il/sci-tea/benari/))
    - [EpiSpin](https://epispin.ewi.tudelft.nl/): Eclipse plug-in for editing and verifying Promela using Spin ([TU Delft](https://swerl.tudelft.nl/twiki/pub/Main/PastAndCurrentMScProjects/thesis-bob-de-vos.pdf))
    - [`promela` parser](https://github.com/johnyf/promela) (BSD-3, Python): parser for Promela using [PLY](https://www.dabeaz.com/ply/ply.html) (Python `lex`-`yacc`) ([Caltech](https://www.cds.caltech.edu/~ifilippi/))
    - [`language-promela`](https://github.com/ubinix-warun/language-promela) (MIT, CoffeeScript): Promela support in Atom
    - [Eclipse Pug-In for SPIN](http://matrix.uni-mb.si/en/science/tools/eclipse-plug-in-for-spin//) (?): (Univ. Maribor, TU Braunschweigin)
    - [st2msc](http://matrix.uni-mb.si/en/science/tools/st2msc-tool/) (?, Java): SPIN trail -> Message Sequence Chart (Univ. Maribor)
    - [Real-Time SPIN](https://www-verimag.imag.fr/~tripakis/rtspin.html): quantitative dense time SPIN extension using Real-Time Promela ([VERIMAG/CNRS](https://www-verimag.imag.fr/~tripakis/index.html))
    - [nano-Promela](https://bitbucket.org/simonhj/nano-promela): tools for nano-Promela language
    - [v-Promela](http://tele.informatik.uni-freiburg.de/leue/visual.html#isorc99): visual Promela (Albert-Ludwigs-Univ. Freiburg)
    - [promela-metamodel](https://code.google.com/p/promela-metamodel/): used to generate Promela from BPEL
    - [Promela library](https://forge.ocamlcore.org/projects/promela/) (BSD-3, OCaml): types for Promela expressions, statements, procs and models as OCaml datastructures, with export to Promela for model checking with SPIN (TU Munchen)
    - [LWAASpin](https://www.pst.ifi.lmu.de/projekte/lwaaspin/) (SPIN's license): SPIN modified to use linear weak alternating automata instead of Buchi automata (Univ. Munchen)
    - [Hugo/RT](https://www.pst.informatik.uni-muenchen.de/projekte/hugo/) (? src by email): XMI or ArgoUML or UTE -> Promela or UPPAAL or KIV or Java or SystemC or Smile machines or UTE model or dot (state machines or interactions) and SPIN or UPPAAL trail -> UML run: UML model translator for model checking, theorem proving, code generation (Univ. Munchen, LORIA/INRIA Nancy)
    - [Pi2Promela](https://lcs.ios.ac.cn/~wp/pi2pro_manual.html) (?, C/Java): compiler from pi-calculus models to Promela, includes GUI ([Chinese Acad. Sciences](https://lcs.ios.ac.cn/~wp/))
    - [pspin](https://github.com/tw33dl3dee/pspin) (?, Python/C): Parallel PROMELA model checker
    - [prob-Promela](https://github.com/hhu-stups/prob-promela): Promela Compiler / Interpreter for ProB (Dusseldorf Univ.)
    - [Promela parser/pretty printer](https://github.com/hguenther/language-promela) (?, Haskell)
    - [sudoku-Promela](https://github.com/davidfischer-ch/sudoku-promela) (EUPL, Shell): mini-project about generating Sudoku grids in Promela
    - [VMSSG](https://www.pst.ifi.lmu.de/~hammer/statespaces/): Model checker state space visualization (Ludwig-Maximilians Univ. Munchen)
    - [promela-metamodel](https://code.google.com/p/promela-metamodel/) (GPL-3)
    - [3Spin](http://3spin.peterd.org/) (FUSC, C): modified version of the Spin model checker version 5.1.7 with advances in the efficiency, configurability, and usability of probabilistic state storage (Northeastern Univ.)
    - [POR](https://www.montefiore.ulg.ac.be/services/verif/po-pack.html) (FUSC, C): partial-order reduction package for SPIN ([Univ. de Liege](https://www.montefiore.ulg.ac.be/services/verif/Welcome-en.html))
    - [ARINC tester](https://www.gisum.uma.es/tools/arinctester/) (?, Java): GUI for SPIN to verify application that contain API calls compliant to ARINC 653 (UMalaga)
    - [SpinRCP](http://lms.uni-mb.si/spinrcp/index.html) (?, Java): An Eclipse-based IDE for Spin. (Univ. of Maribor)
    - [DTSpin](https://www.win.tue.nl/~dragan/DTSpin/) (FUSC, C): extension of Spin with discrete time, is intended for verification of concurrent systems that depend on timing parameters, and uses the specification language DTPromela (Eindhoven Univ. of Technology)
        - [Dtp2dtp](https://homepages.cwi.nl/~sbohte/ustin/EH.html) (?, ?): translator from discrete-time Promela to discrete-time Promela, for proving an embedding of nondeterministic transitions that automatically closes open systems
    - [CPOR-Spin](https://www.win.tue.nl/~dragan/CPOR-Spin/) (FUSC, C): extension of Spin which exploits the hierarchy of the verified system for more efficient verification, using Clustered Partial Order Reduction (CPOR) (Eindhoven Univ. of Technology)
    - [MPI-Spin](https://vsl.cis.udel.edu/mpi-spin/) (GPLv3, C): extension of Spin that adds to Promela functions, types, and constants for modeling parallel programs that use the Message Passing Interface (Univ. of Delaware)
- [TLA+](https://lamport.azurewebsites.net/tla/tla.html): The Temporal Logic of Actions for specifying systems ([Microsoft Research](http://lamport.org))
    - [The TLA+ Video Course](https://lamport.azurewebsites.net/video/videos.html): Lectures about writing specifications, by Leslie Lamport
    - [PlusCal](https://lamport.azurewebsites.net/tla/pluscal.html): An algorithm language with a translator to TLA+
        - [Distributed PlusCal](https://github.com/hebaalkayed/DistributedPlusCal) (Java): extension of PlusCal with threads within processes and variables that represent communication channels
    - [TLA+ Tools](https://lamport.azurewebsites.net/tla/tools.html), (MIT, [Java](https://github.com/tlaplus/tlaplus)): Tools for working with TLA+ specifications:
        - [TLC](https://lamport.azurewebsites.net/tla/tlc.html) (MIT, Java): Model checker for TLA+ specifications
        - [SANY](https://lamport.azurewebsites.net/tla/sany.html) (MIT, Java): Parser and semantic analyzer for TLA+ ([ANTLR](https://www.antlr.org/)-based)
        - [TLATeX](https://lamport.azurewebsites.net/tla/tlatex.html) (MIT, Java): Program for typesetting TLA+ specs
        - [The TLA Toolbox](https://lamport.azurewebsites.net/tla/toolbox.html) (MIT, Java): An IDE for the TLA+ tools (Eclipse-based), includes TLC, SANY, TLATeX, and the PlusCal translator
        - [TLAPS](https://tla.msr-inria.inria.fr/tlaps/content/Home.html): See automated theorem provers section.
        - Tools for working with TLA+ proofs: See automated theorem provers section.
    - [`tla_tools`](https://github.com/joewilliams/tla_tools) (MIT, Shell): Helper tools for using TLA+ (wrappers etc.) ([GitHub](https://github.com/joewilliams))
    - [`tla-bin`](https://github.com/pmer/tla-bin) (MIT, Shell): Command line binaries for the TLA+ language
    - [tla related tools](https://github.com/hhu-stups) (Dusseldorf Univ.)
    - [TEM](https://ls4-www.cs.tu-dortmund.de/RVS/P-TLA/TEM/tem.html) (GPL, Emacs): TLA+ major mode for GNU EMACS 19 (TU Dortmund)
    - [language-tla-pluscal](https://github.com/wysiib/language-tla-pluscal) (MIT, CoffeeScript): TLA+ and PlusCal Language Support in Atom ([Heinrich-Heine-Univ.](https://krin.gs/))
    - [TLAGrammar](https://github.com/agentultra/TLAGrammar) (MIT): Textmate-compatible grammar for TLA+ (used to highlight TLA+ on github)
    - [`vim-scripts/TLA`](https://github.com/vim-scripts/TLA) (GPL, VimL): TLA+ plugin for Gvim
    - [`vim-scripts/tla.vim`](https://github.com/vim-scripts/tla.vim) (?, VimL): Vim syntax highlighting for TLA+
    - [`tla.vim`](https://github.com/hwayne/tla.vim) (MIT, VimL): Vim plugin for TLA+ and PlusCal
    - [eTLA](https://sourceforge.net/projects/etla/) (EPL): TLA+ plugin for Eclipse
    - [textadept-TLA-](https://github.com/Hackerpilot/textadept-TLA-) (MIT, Lua): TLA+ and PlusCal syntax highlighting for Textadept
    - [vscode-tlaplus](https://github.com/alygin/vscode-tlaplus) (MIT, TypeScript): adds support for TLA+ to VS Code
    - [`specifica`](https://github.com/ret/specifica) (MIT, Haskell): TLA+ parser, evaluator, and pretty-printer
    - [`tla-parser-s`](https://github.com/jarjuk/tla-parser-s) (MIT, Ruby): TLA+ parser (Helsinki)
    - TLA+ examples:
        - [TLA Tools examples](https://github.com/tlaplus/Examples) (MIT, TLA+): a collection of TLA+ specifications of varying complexities
        - [CommunityModules](https://github.com/tlaplus/CommunityModules) (MIT, TLA+/Java): TLA+ snippets, operators, and modules contributed and curated by the TLA+ community
        - [TLAPS examples](https://github.com/tlaplus/tlapm/tree/master/examples): TLA+ modules of example specifications distributed with TLAPS
        - [TLAPS library](https://github.com/tlaplus/tlapm/tree/master/library): TLA+ modules distributed with TLAPS and intended to be extended
        - [MultiPaxos](https://github.com/nano-o/MultiPaxos)
        - [Egalitarian Paxos](https://github.com/efficient/epaxos) (CMU, Intel Labs)
        - [Leaderless Byzantine Paxos](https://bitbucket.org/ngunatillaka/leaderless-byzantine-paxos) (UNSW)
        - [Flexible Paxos](https://github.com/fpaxos/fpaxos-tlaplus) (MIT, TLA+): specification and TLC model checking configuration for single shot Flexible Paxos
        - [Raft consensus algorithm](https://github.com/ongardie/raft.tla)
        - [TLA-Library](https://github.com/nano-o/TLA-Library)
        - [Azure Cosmos DB](https://github.com/Azure/azure-cosmos-tla) (MIT, TLA+): specifications (Microsoft)
        - [MongoDB](https://github.com/visualzhou/mongo-repl-tla): simplified part of MongoDB replication system (MongoDB)
        - [Convergence locking](https://github.com/ryansb/heat-tla-model)
        - [TLA+ in TiDB](https://github.com/pingcap/tla-plus) (Apache-2.0, TLA+): specifications for TiDB, an open source distributed HTAP database compatible with the MySQL protocol
        - [Elasticsearch](https://github.com/elastic/elasticsearch-formal-models) (Apache-2.0, TLA+/Isabelle): Formal models of core Elasticsearch algorithms
    - [tTLA+ Browser](https://ls4-www.cs.tu-dortmund.de/RVS/P-TLA/TBR/tbr.html) (FUSC, C): old project about a TLA+ IDE (TU Dortmund)
    - [Tools for TLA](https://ls4-www.cs.tu-dortmund.de/RVS/P-TLA/welcome.html): old TLA+-related project (TU Dortmund)
    - [TLA within ProB](https://www3.hhu.de/stups/prob/index.php/TLA): (Heinrich Heine Univ. Düsseldorf)
        - [`tla2b`](https://github.com/hhu-stups/tla2b) (EPL, Java)
        - [`tla2bAST`](https://github.com/hhu-stups/tla2bAST) (EPL, Java)
        - [`tlc4b`](https://github.com/hhu-stups/tlc4b) (EPL, Java)
    - [`tla-dafny`](https://github.com/jonhnet/tla-dafny) (Apache-2.0, Dafny): An embedding of TLA+ in Dafny
- [LTSmin](https://fmt.cs.utwente.nl/tools/ltsmin/) (BSD-3): model checking, LTS minimization, interface to other tools (Univ. Twente)
- [MoonWalker](https://fmt.cs.utwente.nl/tools/moonwalker/) (Apache-2, C\#): model check CIL bytecode programs ([Mono .NET](https://www.mono-project.com/Main_Page) platform apps), [MoonWalker src](https://code.google.com/p/moonwalker/)(Univ. Twente)
- [DIVINE](https://divine.fi.muni.cz) ([Open Source](https://divine.fi.muni.cz/current/doc/), [C++](https://divine.fi.muni.cz/current/)): Parallel LTL model checker (Masaryk Univ.)
- [PRISM](https://www.prismmodelchecker.org/) (GPLv2, [Java/C](https://github.com/prismmodelchecker/)): Probabilistic Model Checker: discrete/continuous-time Markov chains, timed automata, etc. (Univ. Birmingham, Univ. Oxford)
    - [PRISM tools](https://www.prismmodelchecker.org/other-tools.php)
    - [prism-games](https://www.prismmodelchecker.org/games/) (GPLv2, [Java/C](https://github.com/prismmodelchecker/prism-games)): an extension of PRISM which supports stochastic games
- [STORM](https://www.stormchecker.org) (GPL-3, [C++](https://github.com/moves-rwth/storm)): Probabilistic model checker: Markov chains, MDPs, Markov automata, SMPT, (MI)LP, LP, Bellman, games, parameter synthesis, discrete-time MDPs
    - [`stormpy`](https://github.com/moves-rwth/stormpy): Python interface
- [ePMC](https://iscasmc.ios.ac.cn/?p=1241) (GPLv3, [Java/C](https://github.com/ISCAS-PMC/ePMC)): an extendible probabilistic model checker, reasons about continuous- anhd discrete-time Markov chains, Markov decision processes, stochastic multi-player games, probabilistic parity games, the logics PCTL, PLTL, PCTL\*, with input in formats PRISM and JANI, is successor of the model checker IscasMC (Institute of Software Chinese Academy of Sciences)
- [SPOT](http://spot.lip6.fr/wiki/) (GPL, C++/Python): object-oriented model checking library using TGBA
- [JPF](https://babelfish.arc.nasa.gov/trac/jpf) ([NOSA-1.3](http://javapathfinder.sourceforge.net/NOSA-1.3-JPF.txt)): Java Pathfinder: Java model checking and extensions (NASA Ames)
    - [JPL-nhandler](https://bitbucket.org/nastaran/jpf-nhandler) (GPL-3, Java): JPF extension to delegate execution of SUT methods to host JVM ([York Univ.](https://www.nastaran.ca/))
- [HELENA](https://sourceforge.net/projects/helena-mc/) (GPL-2): high-level Petri nets (Paris 13 Univ.)
- [StEAM](https://steam.cs.uni-dortmund.de/) (C++ ?): C++ model checker (deadlocks, segmentation faults, out of range variables and non-terminating loops) (LS5 Univ. Dortmund)
- [Tulip](https://tulip.lenhardt.co.uk/): LTL model checker of interval Markov chains (recursive also) (Univ. Oxford)
- [PROD](http://www.tcs.hut.fi/Software/prod/) (GPL): efficient reachability analysis (Helsinki Univ. Tech.)
- [KBDD](https://www.cs.rice.edu/CS/Verification/Software/software.html): BDD-based satisfiability solver for modal logic K
- [neco](https://code.google.com/p/neco-net-compiler/) (LGPL, Python/Cython): Petri Net compiler and LTL model checker (Univ. d'Evry-Val d'Essonne, Univ. Evry)
- [PEP](https://sourceforge.net/projects/peptool/) (GPL-2): modelling and verification framework for parallel systems, interfaces to SPIN, SMV, INA, FC2Tools (SDL, Petri nets)
- [cunf](https://code.google.com/p/cunf/) (GPL-3): Toolset for unfolding-based verification of Petri nets extended with read arcs ([ENS Cachan](https://www.lsv.ens-cachan.fr/~rodriguez/))
- [daj](https://github.com/motib/daj) ([GPLv2](https://code.google.com/p/daj/), Java): interactive, visual aid for studying execution of distributed algorithms ([The Weizmann Institute of Science](https://www.weizmann.ac.il/sci-tea/benari/))
- [FC2Tools and Autograph](https://www-sop.inria.fr/meije/verification/): implementation of process algebra theory, verification by compositional reductions and abstraction, explicit/implicit BDD, FC2 file exchange format (INRIA, Ecole des Mines/CMA)
- [Murphi](https://www.cs.utah.edu/formal_verification/Murphi/), [original Murphi](https://verify.stanford.edu/dill/murphi.html) (BSD-like, C++): enumerative, own input language (Unity style: guard -> action), e.g. used by Microprocessor industry to verify cache coherence protocols (Univ. Utah, Stanford)
    - [Eddy Murphi](https://www.cs.utah.edu/formal_verification/EddyMurphi/): parallel version of Murphi (Univ. Utah)
    - [CMurphy](http://mclab.di.uniroma1.it/site/index.php/software/18-cmurphi) (Univ. Roma)
    - [CMurphi](https://www.di.univaq.it/gdellape/lamoka/page.php?pid=246&lid=en) (L'Aquila Univ.)
    - [PReach](https://bitbucket.org/jderick/preach/wiki/Home) (BSD, Erlang): Distributed Explicit State Model Checker based on Erlang and Murphi (Univ. British Columbia, Intel)
    - [MPI Murphi port](https://www.cs.utah.edu/formal_verification/software/murphi/murphi.hemanth/index.only_hemanth.html) (Univ. Utah)
- [APMC](https://sylvain.berbiqui.org/apmc) (FUSC, C/Java): approximate distributed for fully probabilistic systems, PCTL, PLTL (Univ. de Caen Basse-Normandie)
- [Vaucanson](https://www.lrde.epita.fr/cgi-bin/twiki/view/Vaucanson/) (GNU, C++): finite state machine manipulation platform, lib of tools on top (EPITA)
- [Genealogy](https://spot.lip6.fr/wiki/EmptinessCheckAlgorithms) of Emptiness-Checking Algorithms ([EPITA](https://www.lrde.epita.fr/~adl/))
- [NIPS](https://www.foldr.org/~michaelw/projects/gitweb?p=nips-vm.git;a=summary) (GNU, C/Perl): A virtual machine for state space generation (RWTH Aachen)
- [VMSSG Statespace Converter](http://www.pst.informatik.uni-muenchen.de/~hammer/statespaces/manual.html) (GPL, Java): process, analyze, display statespace graphs produced by modified VMSSG virtual machine, [state space gallery](https://www.pst.ifi.lmu.de/~hammer/statespaces/index.html), ([Univ. Munchen](http://www.pst.ifi.lmu.de/Personen/ehemalige/hammer/hammer/view))
- [Synet](http://www.irisa.fr/s4/tools/synet/) (OCaml): Synthesizer of distributable bounded Petri nets from Finite Automata ([INRIA/IRISA](http://www.irisa.fr/prive/Benoit.Caillaud/Benoit_Caillauds_Professional_homepage/Welcome.html))
- [Motion Grammar Kit](https://github.com/golems/motion-grammar-kit) (BSD-2, Common Lisp/C): Automata manipulation, supervisory control, C code generation (Georgia Tech.)
- [PAT](https://en.wikipedia.org/wiki/PAT_%28model_checker%29) (?, C\#): Process Analysis Toolkit, a model checker, with GUI, model editor, simulator, POR, symmetry reduction (Nat. Univ. Singapore)
- [NorMC](https://github.com/pkazmierczak/NorMC) (BSD-3, Haskell): Norm compliance temporal logic model checker (Univ. Bergen)
- [Copper](https://www.sei.cmu.edu/predictability/tools/copper/index.cfm) (FUSC, ?): MC for concurrent message-passing C programs (CMU)
- [Magic](https://www.cs.cmu.edu/~chaki/magic/) (?): Check C language conformance between component specifications and their implementations using counterexample guided abstraction refinement, concurrent and compositional (CMU, Univ. Wisconsin, Univ. Oxford, TU Vienna, Univ. Lugano)
- [Bogor](https://bogor.projects.cis.ksu.edu/manual/)
- [BLAST](http://mtc.epfl.ch/software-tools/blast/index-epfl.php) (Apache, OCaml/C): MC for C programs using counterexample-driven automatic abstraction refinement (UC Berkeley, EPFL, UCSD, UCLA, Simon Fraser Univ.)
- [Scoot](https://www.cprover.org/scoot/) (?): Static analysis of SystemC, model extraction to pass to SatAbs or CBMC, C++ re-synthesis (ETH)
- [VCEGAR](https://www.cs.cmu.edu/~modelcheck/vcegar/) (?): Check safety (assertions) of Verilog, using word level predicate abstraction and refinement (CMU, Oxford Univ.)
- [GMC](https://d3s.mff.cuni.cz/~sery/gmc/index.html) (LGPL, C/C++): MC for C/C++ taking GIMPLE as input (Charles Univ. Prague)
- [AIR](https://www.contrib.andrew.cmu.edu/~schaki/publications/NFM-2009.html) (?): Safety MC of Assembly using predicate abstraction and counterexample guided abstraction refinement ([CMU](https://www.contrib.andrew.cmu.edu/~schaki/index.html))
- [FShell](https://forsyte.at/software/fshell/) (Apache): Interactive and Scripting testing environment for C programs, frontend for software model checkers, dispatches queries to analysis tools (TU Wien)
- [CPA/Tiger](https://forsyte.at/software/cpatiger/) (?): Predicate-abstraction based test input generator for C programs, uses CPAchecker (TU Wien)
- [CPAchecker](https://cpachecker.sosy-lab.org/) (Apache-2.0, [SWIG/Java/C](https://github.com/sosy-lab/cpachecker)): Configurable software verification (Univ. Passau)
- [crest](https://code.google.com/p/crest/) (BSD-3): Automatic test generation tool for C, inserts instrumentation code and solves the generated symbolic constraints using Yices (UC Berkeley)
    - [ConCREST](https://forsyte.at/software/concrest/) (?): Concolic testing tool for multi-threaded C programs (Univ. Toronto, TU Wien)
- [ByMC](https://forsyte.at/software/bymc/) (?, OCaml): Byzantine MC for parameterized model checking of (threshold-guarded) fault-tolerant distributed algorithms in Promela extension using SPIN, Yices (TU Wien)
- [iLTL](https://osl.cs.illinois.edu/software/iltl/index.html) (BSD): MC for iLTL, which specifies temporal changes of expected rewards of a Markov process ([UIUC](https://sites.google.com/site/youngminkwon/))
- [Copilot](https://leepike.github.io/Copilot/) (BSD-3, Haskell): A (Haskell DSL) stream language for generating hard real-time C code (NASA, Galois Inc., National Inst. Aerospace, Ecole Normale Superieure, TU Ilmenau, Univ. Copenhagen)
- [mCRL2](https://www.mcrl2.org/release/user_manual/index.html) (Boost Software License, C++): Formal specification language with an associated toolset for modelling, validation and verification of concurrent systems and protocols: linearisation, simulation, state-space exploration, visualization and tools to optimise and analyse specifications, μ-calculus (TU Eindhoven, LaQuSo, CWI, Univ. Twente)
- [Mobility Workbench](https://www.it.uu.se/research/group/mobility/mwb) (?, SML): π-calculus MC for mobile concurrent systems (Uppsala Univ.)
- [MMC](https://www.cs.sunysb.edu/~lmc/mmc/) (?, ?): π-calculus and alternation-free μ-calculus Local MC, implemented using the XSB tabled logic programming system (Stony Brook Univ.)
- [XMC](https://www.cs.sunysb.edu/~lmc/) (?, ?): Local MC for processes specified in XL, a version of value-passing CCS, and the alternation-free modal μ-calculus, implemented using the XSB tabled logic programming system (Stony Brook Univ.)
- [MMCsp](https://lcs.ios.ac.cn/~wp/mmc_sp_manual.html) (?, C/Java): Compiler from simple probabilistic π-calculus to PRISM models, built on XSB (Ecole Polytechnique, Oxford, INRIA)
- [ASTG](https://lcs.ios.ac.cn/~wp/astg_manual.html) (?, OCaml/C): TLCE-based symbolic test generator (Chinese Acad. Sciences)
- [LMNtal, LaViT](https://www.ueda.info.waseda.ac.jp/lmntal/) (BSD, C/C++/Java): MC and graphical tools LMNTal language based on hierarchical graph rewriting (Waseda Univ.)
- [Finite Automata Model Checker](https://bitbucket.org/jwright/finite-automata-model-checker) (CCAS-3, C++)
- [v-n](https://code.google.com/p/v-n/) (GPL-2, Java): NDFA visualization and (random or guided) simulation, find and display accepting computations ([The Weizmann Institute of Science](https://en.wikipedia.org/wiki/Mordechai_Ben-Ari))
- [py-powerset-construction](https://code.google.com/p/py-powerset-construction/) (GPL-3, Python): convert NFA-\lambda to DFA, using dot as input
- [Zing](https://research.microsoft.com/en-us/projects/zing/) (MIT, [C\#](https://github.com/ZingModelChecker/Zing)): State exploration of concurrent software systems (Microsoft Research)
- [SeaHorn](https://github.com/seahorn/seahorn) (BSD, C): an LLVM based verification framework
- [SCRAM](https://github.com/rakhimov/scram)(GPL-3, C++/Python): Probabilistic risk analysis (static fault trees, common cause failure models, Monte Carlo) with input from and output to Open-PSA model exchange format files
- [RISCAL](https://www.risc.jku.at/research/formal/software/RISCAL/) (GPL-3, Java): Specification language and software system for describing mathematical algorithms, and validating their correctness by execution/evaluation ([JKU/RISC](https://www.risc.jku.at/home/schreine))
- [Properties of State Spaces](https://www.fi.muni.cz/~xpelanek/state_spaces/summary.html)
- [symmetrytools](https://github.com/afd/symmetrytools) (?, Java): Tools for symmetry reduction in model checking (Univ. of Glasgow)
- [Mscgen](https://www.mcternan.me.uk/mscgen/) (GPLv2, C): Message Sequence Chart Renderer ([wiki entry](https://en.wikipedia.org/wiki/MscGen))
    - [`mscgen-preview`](https://atom.io/packages/mscgen-preview) (GPLv3, [CoffeeScript/JavaScript](https://github.com/sverweij/atom-mscgen-preview)): Write and preview sequence charts with MscGen and its brethren with `ctrl-shift-G`
    - [`sphinxcontrib-mscgen`](https://pypi.org/project/sphinxcontrib-mscgen) (Public Domain, Python): Allow mscgen-formatted Message Sequence Chart (MSC) graphs to be included in Sphinx-generated documents inline
- [TTool](https://ttool.telecom-paris.fr/) (CeCILL, [Java/C++](https://gitlab.telecom-paris.fr/mbe-tools/TTool/)): toolkit dedicated to the edition of UML and SysML diagrams, and to the simulation and formal verification (safety, security, performance) of those diagrams
- [Gadara](http://gadara.eecs.umich.edu/software.html) (?, Java): discrete-control synthesis from Petri nets (Univ. of Michigan):
    - [Petri net generator](http://gadara.eecs.umich.edu/tools/gadara_src.zip)
    - [multi-threaded Petri net verifier](http://gadara.eecs.umich.edu/tools/gadara_src.zip): single-bit unique encoding of states that are enumerated to explore the state set
- [PROD](http://www.tcs.hut.fi/Software/prod/) (GPLv2, C): reachability analyzer for Pr/T-nets with: stubborn sets, sleep sets, on-the-fly tester based verification, on-the-fly LTL model checking, CTL model checking (Helsinki Univ. of Technology)

### Symbolic
- [Apalache](https://github.com/informalsystems/apalache) (Apache-2, Scala): symbolic model checker for TLA+
- [SMV](https://www.cs.cmu.edu/~modelcheck/smv.html) (?): CTL symbolic model checker (CMU)
    - [Cadence SMV](http://www.kenmcmil.com/smv.html) (FUSC): CMU SMV extension: backward compatible more expressive mode description language, synthesizable VERILOG, compositional verification, CTL or LTL or FSA or embedded assertions, GUI (Cadence)
- [NuSMV](https://nusmv.fbk.eu/) (LGPL): Symbolic model checking (FBK, CMU, Univ. Genoa, Univ. Trento)
    - [PyNuSMV](https://lvl.info.ucl.ac.be/Tools/PyNuSMV) (LGPL-2, Python): python interface to NuSMV ([UCLouvain](https://lvl.info.ucl.ac.be/))
    - [SMView](https://github.com/ArnoVanLumig/smview) (BSD, JavaScript/Python): web interface to NuSMV (TU Eindhoven)
    - [gNuSMV](https://nusmv.fbk.eu/gnusmv/) (LGPL, ?): GUI for NuSMV v2 (FBK)
    - [nusmv-tools](https://code.google.com/a/eclipselabs.org/p/nusmv-tools/): two metamodels based on Eclipse modeling framework, Eclipse editor, model analyzer, Java API to NuSMV
    - [nuseen](https://code.google.com/a/eclipselabs.org/p/nuseen/): Eclipse-based environment for NuSMV
- [nuXmv](https://es-static.fbk.eu/tools/nuxmv/index.php): extends NuSMV using state-of-the-art SAT-based algorithms and MathSAT5 (Fondazione Bruno Kessler)
- [abc](https://www.eecs.berkeley.edu/~alanmi/abc/abc.htm) (FOSS, [C](https://github.com/berkeley-abc/abc)): System for Sequential Logic Synthesis and Formal Verification: A growing software system for synthesis and verification of binary sequential logic circuits appearing in synchronous hardware designs; ABC combines scalable logic optimization based on And-Inverter Graphs (AIGs), optimal-delay DAG-based technology mapping for look-up tables and standard cells, and innovative algorithms for sequential synthesis and verification (UC Berkeley)
- [Mocha](http://mtc.epfl.ch/software-tools/mocha/), also [here](https://www.cis.upenn.edu/~mocha/) (BSD, two implementations: Java, C/Tcl/Tk): Interactive environment for system specification (reactive modules language), execution (randomized, guided, mixed), requirement specification (Alternating Temporal Logic, superset of CTL), ATL MC, implementation verification (EPFL, UC Berkeley, UPenn, SUNYSB)
- [CBMC](https://www.cs.cmu.edu/~modelcheck/cbmc/) (BSD-4, [SWIG/C++/C](https://github.com/diffblue/cbmc)): Bounded model checker for ANSI-C, C++, SystemC, Scoot, uses Boolector or MathSAT or Z3 (CMU, Oxford Univ.)
    - [Eclipse plugin](https://www.cprover.org/eclipse-plugin/) (EPL, [Java](https://github.com/diffblue/eclipse-cbmc)): Eclipse plugin for CBMC
    - [Visual Studio plugin](https://www.cprover.org/visual-studio/)
    - [JBMC](https://www.cprover.org/jbmc/) (BSD-4, [C++](https://github.com/diffblue/cbmc/tree/develop/jbmc)): bounded model checking tool for verifying Java bytecode
    - [Symex](https://github.com/diffblue/symex) (BSD-4, C++): symbolic execution tool for C and C++ programs, based on CBMC. It supports C89, C99, most of C11 and most compiler extensions provided by gcc and Visual Studio (CMU, Oxford Univ.)
    - [EBMC and HW-CBMC](https://www.cprover.org/ebmc/) (BSD-3, [C++](https://github.com/diffblue/hw-cbmc)): bounded model checker for the Verilog language (and other HW specification languages), based on CBMC (CMU, Oxford Univ.)
    - [2LS](https://github.com/diffblue/2ls) (BSD-4, C++): Static Analyzer and Verifier for C programs, built upon the CPROVER framework (CMU, Oxford Univ.)
    - [k-induction](https://github.com/moves-rwth/cbmc-with-kInduction) (MIT, Python): enables any C bounded model checker to be employed for k-induction over one-loop embedded-style C programs. Tested with CBMC.
    - [ESBMC](http://esbmc.org/) (several, [C++](https://github.com/esbmc/esbmc)): context-bounded model checker based on a satisfiability modulo theories (SMT) solver for the verification of single- and multi-threaded C/C++ programs, with Python and C++ APIs, and based on CBMC (Federal Univ. of Amazonas, Univ. of Bristol, Univ. of Manchester, Univ. of Stellenbosch, and Univ. of Southampton)
- [EBMC](https://www.cprover.org/ebmc/) (BSD-5): Bounded Model Checker for hardware designs, inputs: Netlists/ISCAS89 or Verilog or SMV, exports: DIMACS CNF or SMT-LIB (CMU, ETHZ, Oxford Univ.)
- [jStar](http://www.jstarverifier.org/) (BSD-3, OCaml): (Queen Mary Univ. London, Cambridge Univ., ETH)
- [coreStar](https://github.com/seplogic/corestar) (BSD-3, OCaml): symbolic execution engine for analysis and verification with separation logic (Queen Mary Univ. London, Univ. Cambridge)
- [JSCert JuS](http://jscert.org/index.html): Certified JavaScript (Imperial College, INRIA)
    - [jabstr](https://github.com/MatkoBotincan/jabstr) (LGPL, Ocaml): jStar plugin for numerical abstractions
- [LStar](https://bitbucket.org/jvillard/lstar/wiki/Home) (BSD-3, OCaml): automatic prover for programs written in bitcode using separation logic (UCL)
- [VIS](http://vlsi.colorado.edu/~vis/): logic circuit simulation, circuit verification, fair CTL model checking, logic synthesis via hierarchy restructuring [UC Berkeley, Univ. Colorado at Boulder, Univ. Texas at Austin]
- [VerICS](http://verics.ipipan.waw.pl/start) (FUSC, Java): SAT verification of timed and multi-agent systems modeled by networks of communicating automata (Polish Academy of Sciences)
- [Augur 2](http://www.ti.inf.uni-due.de/research/tools/augur2/) (GPL-2, C++): verification of systems described by (attributed) graph transformations using approximated unfoldings ([Univ. Duisburg-Essen](http://www.ti.inf.uni-due.de/people/koenig/))
- [Mercury](http://rodrigotaclasaad.drupalgardens.com/content/mercury): Parallel Local Sub-CTL Model Checking [LAAS-CNRS]
- [Boogie](http://research.microsoft.com/en-us/projects/boogie/) ([Ms-PL](http://boogie.codeplex.com/license), F\#/C\#): Intermediate verification language, intended as a layer on which to build program verifiers for other languages (Microsoft Research)
    - [SymDiff](http://research.microsoft.com/en-us/projects/symdiff/default.aspx): Language-independent differential program analysis (C, Boogie front-ends available) (Microsoft Research)
- [VCC](http://research.microsoft.com/en-us/projects/vcc/default.aspx) (MIT, [C\#/F\#/C/Perl](https://github.com/microsoft/vcc)): static verifier for concurrent C programs (Microsoft Research)
- [HAVOC](http://research.microsoft.com/en-us/projects/havoc/default.aspx) (?): for C in the presence of pointer manipulations, unsafe casts and dynamic memory allocation (Microsoft Research)
- [Dafny](https://github.com/dafny-lang/dafny) (MIT, C\#): imperative object-based language with built-in specification constructs and static program verifier for functional correctness, [try it online](https://rise4fun.com/Dafny/) ([Microsoft Research](http://research.microsoft.com/en-us/um/people/leino/))
    - [vim plugin](https://github.com/mlr-msft/vim-loves-dafny) (MS-PL, Vim script): Vim plugin for Dafny, with `.dfy` file extension, syntax highlighting, syntax checking
    - [`vim-dafny`](https://github.com/benknoble/vim-dafny) (BSD-3, Vim script): Dafny language plugin for vim, based on the previous tool
    - [sublime Dafny](https://github.com/erggo/sublime-dafny): Sublime Text 2 plugin for Dafny. Provides verifing and syntax highlighting ([Imperial College London](http://tomas.virgl.net/))
    - [Dafny VSCode](https://github.com/DafnyVSCode/Dafny-VSCode) (MIT, TypeScript): infrastructure necessary to support Dafny for Visual Studio Code
    - [eclipse-dafny](https://github.com/jkuehnemundt/eclipse-dafny) (GPLv3, Java): enables Dafny language support in Eclipse
    - [spacemacs-boogie-friends](https://github.com/dschoepe/spacemacs-boogie-friends) (GPLv3, Emacs Lisp): Spacemacs layer for working with Dafny, Boogie, and Z3
    - [DIVE](https://github.com/mattulbrich/dive) (GPLv3, Java): graphical proof front end for programs written and specified in Dafny that supports different types of user guidance for proofs
    - [DafnyR](https://github.com/YuyanBao/DafnyR) (MIT, C\#): experimental tool for sequential program specification and verification. Variant of Dafny inspired by region logic. Built on a fine-grained region logic, allows one to use several styles of specifying the frame properties in sequential programs: dynamic frames, region logic and separation logic.
    - [`dfydoc`](https://github.com/nhweston/dfydoc) (?, Scala): documentation generator for Dafny
    - [python-to-dafny-converter](https://github.com/eringrant/python-to-dafny-converter) (GPLv3, Python): translates Python code to Dafny (UC Berkeley)
    - [dafny-to-c](https://github.com/shawa/dafny-to-c) (?, Shell): basic sed-based translator from Dafny to C
    - [Dione](https://github.com/cyphyhouse/Dione) (NCSA, Python/Dafny): protocol verification system built with Dafny for Input/Output Automata (UIUC)
- [CakeML](https://cakeml.org) (BSD-3, [ML](https://github.com/CakeML/cakeml)): a verified implementation of ML: functional programming language and an ecosystem of proofs and tools built around the language, including a proven-correct compiler that can bootstrap itself
- [Idris](https://docs.idris-lang.org/en/latest/tutorial/theorems.html) (BSD-3, [Haskell/C](https://github.com/idris-lang/Idris-dev)): a dependently typed functional programming language that allows propositional equalities to be declared, so that theorems about programs can be stated and proved (Univ. of St Andrews)
- [Spec\#](http://specsharp.codeplex.com/) ([FUSC](http://specsharp.codeplex.com/license), C\#): Object-oriented .NET programming language with design-by-contract features for method pre-/postconditions and object invariants, non-null type system (Microsoft Research)
- [Whiley](https://github.com/DavePearce/Whiley) (BSD-3, Java/C/): Object-oriented and functional programming language with static checking, including: divide-by-zero, array out-of-bounds and null dereference errors ([Victoria Univ. of Wellington](http://homepages.ecs.vuw.ac.nz/~djp/))
- [Why3](http://why3.lri.fr/) (GPl-2, OCaml): platform for deductive program verification in WhyML, uses external theorem provers, extracts OCaml from WhyML ([INRIA, Univ. Paris Sud, CNRS, LRI](https://toccata.lri.fr/))
    - [EasyCrypt](https://software.imdea.org/projects/certicrypt/) (?, OCaml): toolset for reasoning about relational properties of probabilistic computations with adversarial code (IMDEA Software Institute, Microsoft Research)
    - [GNATprove](https://www.open-do.org/projects/hi-lite/gnatprove/) (GPL): Ada 2012 prover
    - [Krakatoa](http://krakatoa.lri.fr/): Java verification
    - [BWare](http://bware.lri.fr/index.php/BWare_project): discharging proof obligations generated by Atelier B using multiple provers
    - [MiniMaple](https://www.risc.jku.at/people/mtkhan/dk10/software.html) (GPL-3, Java): Software for formal specification and verification of Maple programs by translation to Why3ML ([JKU](https://www.risc.jku.at/home/mtkhan))
- [KeY](https://en.wikipedia.org/wiki/KeY) (GPL, Java): Formal verifier with input HML or OCL specs for JAVA, via dynamic logic thms (Karlsruhe Inst. Tech., TU Darmstadt, Chalmers Univ. Tech.)
    - [KeY-Hoare](http://www.key-project.org/download/hoare/) (GPL, Java): Hoare calculus with updates, extension of KeY (KIT, TUD, Chalmers)
    - [KeYmaera](http://symbolaris.com/info/KeYmaera.html) (GPL, Java): Theorem prover for hybrid systems: deductive, real algebraic, and computer algebraic prover technologies ([CMU](http://symbolaris.com/andre.html))
    - [KeYmaeraD](http://symbolaris.com/info/KeYmaeraD.html), its [github](https://github.com/keymaerad/KeYmaeraD) (BSD-3, Scala): Distributed theorem prover for distributed hybrid systems using Quantified differential dynamic logic (QdL) ([CMU](http://symbolaris.com/andre.html))
    - [SPHINX](https://www.cs.cmu.edu/afs/cs/Web/People/smitsch/tools.html) (?): Eclipse plugin for textual and graphical modeling editors to define cyber-physical system structure, discrete/continuous dynamics ([CMU](https://www.cs.cmu.edu/afs/cs/Web/People/smitsch/index.html))
- [j-algo](http://j-algo.binaervarianz.de/index.php?language=en) (GPL, Java): Algorithm visualization tool (TU Dresden)
- [Verus](https://www.cs.cmu.edu/~modelcheck/verus.html) (?): Language for real-time systems, CTL symbolic MC, compilation into state-transition graph (CMU)
- [UCLID](https://www.cs.cmu.edu/~uclid/) (BSD-like): Model and verify nfinite-state systems with variables of integer, Boolean, function, and array types, term-level bounded model checking, correspondence checking, deductive verification, and predicate abstraction-based verification, and stand-alone decision procedure for the theories of uninterpreted functions and equality, integer linear arithmetic, and arrays (CMU, UC Berkeley)
- [CBMC-GC](https://forsyte.at/software/cbmc-gc/) (?): C compiler in the context of Secure Two-party Computation (STC) (TU Wien, TU Darmstadt, CASED, CrypTool Project)
- [Chic](https://en.wikipedia.org/wiki/CHIC_%28electronics%29) (BSD, Java): Modular verifier for behavioral compatibility checking of hardware and software systems (UC Berkeley)
- [BLAST](http://mtc.epfl.ch/software-tools/blast/index-epfl.php) (Apache, OCaml): software MC for C using Lazy abstraction (UC Berkeley, EPFL, UCSD, UCLA, Simon Fraser Univ.)
- [CRefine](http://www.cs.york.ac.uk/circus/tools/refinement.php) (?, Java): Verifies `Circus` specs purely by applying various well-proved refinement laws, requires veriT (Univ. York)
- [UTP and Cirus Theories in ProofPower-Z](http://www.cs.york.ac.uk/circus/tools/utp.php) (?, ?): embedding the theories (relations, designs, reactive processes) of UTP in the theorem prover ProofPower-Z, formal proofs can be mechanically constructed (Univ. York)
- [Circus Type Checker](http://www.cs.york.ac.uk/circus/tools/type.php) (? , Java): Syntax type checker for Circus specifications (Univ. York, UFPCI)
- [JCircus](http://www.cs.york.ac.uk/circus/tools/jcsp.php) (?, Java): Automatically translate Circus programs into Java, for the purpose of animation and simulation (Univ. York)
- [ClawCircus](http://www.cs.york.ac.uk/circus/tools/control.php) (?, Java): Java-based tools primarily for generating Circus models from Simulink (Univ. York)
- [Circus Parser](https://sourceforge.net/projects/czt/) (GPL-2, Java): Included in Community Z tools (Univ. York)
- [Rodin](http://www.event-b.org) (EPL, Eclipse): Eclipse-based platform for refinement and mathematical proof of Event-B (Univ. Southampton)
- [CheckFence](http://checkfence.sourceforge.net) (BSD, OCaml): SAT-based analysis of C code implementing concurrent data types (UPenn)
- [Daikon](https://en.wikipedia.org/wiki/Daikon_%28system%29) (MIT, Java): Dynamic invariant detection for C/C++, Eiffel, IOA, Perl (MIT)
- [Tip](https://github.com/niklasso/tip) (?, C++/C): (Temporal Induction Prover) SAT based model checker ([Chalmers Univ.](http://minisat.se/Authors.html))
- [alloy](http://alloy.mit.edu/alloy/): Language inspired by Z spec language and Tarski's relational calculus for implicitly describing structures and tool for exploring and generating counterexamples (MIT)
- [Kodkod](http://alloy.mit.edu/kodkod/) (MIT, Java): SAT-based constraint solver for first order logic with relations, transitive closure, bit-vector arithmetic, and partial models, with finite model finder and minimal unsatisfiable core extractor (MIT)
- [Rebeca](https://rebeca-lang.org/) (GPLv2, [Java](https://github.com/rebeca-lang)): Reactive Objects Language is an actor-based language with a formal foundation, designed in an effort to bridge the gap between formal verification approaches and real applications, with a set of [tools](https://rebeca-lang.org/tools)
- [IVy](https://microsoft.github.io/ivy/) (MIT, [Python](https://github.com/Microsoft/ivy)): A tool for specifying, modeling, implementing and verifying protocols (MSR, Tel Aviv Univ., UCB)
- [`mypyvy`](https://github.com/wilcoxjay/mypyvy) (MIT, Python): language for symbolic transition systems, inspired by Ivy, and tool that takes an input file describing a symbolic transition system and can perform various tasks such as inductive invariant checking and inference (Univ. of Washington)
- [PyCSP](https://code.google.com/p/pycsp/) (MIT, Python): communicating sequential processes in Python (Aarhus Univ.)
- [FDR2](https://en.wikipedia.org/wiki/FDR2): Refinement checker for communicating sequential processes (Oxford Univ.)
- [KRATOS](https://es-static.fbk.eu/tools/kratos/): MC for sequential and cooperative multi-threaded C programs, verifying safety properties (Bruno Kessler Found.)
- [Mr. Waffles](http://mrwaffles.gforge.inria.fr/index.html) (GPL-2, Python): bare-bones CTL MC (Nancy Univ., LHS/LORIA, ESEC R&D)
- [Peirce-Logic](https://github.com/CurryBoy/Peirce-Logic) (BSD-3, JS): Existential Graph proof system ([RPI](http://www.dimit.me/))
- [VSE](https://www.dfki.de/vse/projects/vse.html): verification support environment (DFKI, IST, Univ. Ulm, DASA)
    - [VSE II](https://www.dfki.de/vse/projects/vse-short.html): Enhancing VSE with concurrency, structural deduction, and an integrated theorem prover
- [Leon](https://lara.epfl.ch/w/leon) (Scala): automated synthesis and verification of Scala programs (EPFL)
- [Eldarica](https://lara.epfl.ch/w/eldarica) (Java): predicate abstraction engine, generates Abstract Reachability Tree (ART) using lazy abstraction (EPFL)
    - [Eldarica-P](http://www.philipp.ruemmer.org/eldarica-p.shtml) (?, Java): reachability checker for unbounded Petri nets (EPFL)
- [Bug-Assist](https://bugassist.mpi-sws.org/) (?): error localization in ANSI-C solving MAX-SAT (Max Planck Inst.)
- [CADP](http://www.inrialpes.fr/vasy/cadp.html) (FUSC): compilers, equivalence checking tools, model-checkers for temporal logics and μ-calculus, verifications: enumerative, on-the-fly, symbolic using BDD, etc. (INRIA)
- [MONA](https://github.com/cs-au-dk/MONA) (GPL-2, C/C++): Decision procedure for monadic second-order logic on finite strings and trees ([Aarhus Univ.](https://www.brics.dk/mona))
- [Boom](https://www.cprover.org/boom/) (BSD): Model checking of Boolean programs (ETHZ, Oxford Univ.)
- [MCTK](http://www.kailesu.net/MCTK/) (LGPL, C): model checker for epistemic logic as modification of CUDD and NuSMV ([Griffith Univ.](http://www.kailesu.net/))
- [SMCDEL](https://github.com/jrclogic/SMCDEL) (GPL-2, Haskell):  model checker for Dynamic Epistemic Logic. (ILLC, University of Amsterdam)
- [SymDIVINE](https://github.com/yaqwsx/SymDIVINE) (MIT, C++): a tool for control explicit/data symbolic bit-precise LTL verification of parallel C/C++ programs using LLVM bitcode as intermediate representation [Masaryk Univ.](https://anna.fi.muni.cz/~xbauch/symdivine.html)
- [IC3](https://github.com/arbrad/IC3ref) (MIT, C++): IC3 reference implementation ([Stanford](https://theory.stanford.edu/~arbrad/))
- [Overture](https://github.com/overturetool/overture) (GPL-3.0, Java): An IDE for developing and analyzing VDM models.
- [Smallfoot](http://www0.cs.ucl.ac.uk/staff/p.ohearn/smallfoot/) (QPL, OCaml): Automatic verification tool that checks separation logic specifications of sequential and concurrent programs that manipulate recursive dynamically-allocated (linked) data structures.
- [Cave](https://people.mpi-sws.org/~viktor/cave/) (BSD-style, OCaml): automated verification tool for proving memory safety and linearizability (that is, atomicity and functional correctness) of concurrent data structures
- [sally](https://sri-csl.github.io/sally/) (GPLv2, [C++](https://github.com/SRI-CSL/sally)): Model checker for infinite-state systems described as transition systems, includes BMC, k-induction, IC3 (SRI/CSL)
- [Sviss](https://www.cs.ox.ac.uk/people/thomas.wahl/Sviss/) (?, C++): Symbolic CTL model checker with symmetry reduction, using CUDD 2.4.1 (ETHZ, UT Austin, Univ. of Oxford)
- [Symbolic Java Pathfinder](https://github.com/SymbolicPathFinder/jpf-symbc) (Apache-2.0, Java): symbolic execution for Java bytecode (NASA, Univ. of Nebraska)
- [OpenJML](https://www.openjml.org) (GPLv2, [Java](https://github.com/OpenJML/OpenJML)): program verification tool for Java programs that allows checking specifications of programs annotated in the [Java Modeling Language](http://www.jmlspecs.org), using SMT solvers including Z3, CVC4, and Yices. Includes both static checking and runtime assertion checking facilities. (Univ. of Central Florida)
- [ProVerif](https://en.wikipedia.org/wiki/ProVerif) (GPLv2, [OCaml](https://prosecco.gforge.inria.fr/personal/bblanche/proverif/)): automatic cryptographic protocol verifier, in the Dolev-Yao model. Based on a representation of the protocol by Horn clauses. It can handle many different cryptographic primitives, including shared- and public-key cryptography (encryption and signatures), hash functions, and Diffie-Hellman key agreements, specified both as rewrite rules or as equations. Can prove secrecy, authentication, strong secrecy, equivalences between processes that differ only by terms (Inria, École Polytechnique)
    - [StateVerif](https://markryan.eu/research/statverif/) (GPLv2, OCaml): extends the ProVerif process calculus with constructs for explicit state, in order to be able to reason about protocols that manipulate global state
    - [ProVerif-ATP](https://github.com/darrenldl/ProVerif-ATP) (MIT and GPLv2, OCaml): Combining ProVerif and Automated Theorem Provers for Security Protocol Verification
- [CryptoVerif](https://en.wikipedia.org/wiki/CryptoVerif) (CeCILL-B, [OCaml](https://prosecco.gforge.inria.fr/personal/bblanche/cryptoverif/)): automatic protocol prover sound in the computational model. It can prove secrecy, correspondences, which include in particular authentication. It can handle in particular symmetric encryption, message authentication codes, public-key encryption, signatures, hash functions. (Inria)
    - [cryptoverif-completion](https://github.com/blipp/cryptoverif-completion) (?, Configure/Makefile): Using the readline wrapper `rlwrap` it introduces line editing, history and also some very basic completion support to the interactive mode in CryptoVerif without the need to modify CryptoVerif itself.
    - [CyrptoVerif fork](https://github.com/mgrabovsky/cryptoverif) (CeCILL-B, OCaml): Python implementations for CryptoVerif 1.23
    - [Cyrptoverif fork Python library](https://github.com/mgrabovsky/cryptoverif-py-lib) (MIT and CeCILL-B, Python): contains the supporting library for the CryptoVerif Python implementations fork
- [FS2PV](http://research.microsoft.com/en-us/downloads/d54de3ef-085e-47f0-b7dc-8d56c858aba2/default.aspx) (FUSC, F\#/OCaml): verification tool that compiles cryptographic-protocol implementations in a first-order subset of F\# to a formal pi-calculus model. This pi-calculus model then can be analyzed using ProVerif to prove the desired security properties or to find security flaws. (Microsoft Research)
- [TulaFale](http://research.microsoft.com/en-us/downloads/a91c6322-ae04-4b7c-9f8b-908f094d7a15/default.aspx): specification language for writing machine-checkable descriptions of SOAP-based security protocols and their properties, based on the pi calculus plus XML syntax, logical predicates, and correspondence assertions. The tool compiles TulaFale into the applied pi calculus, and then runs Blanchet's resolution-based protocol verifier. (Microsoft Research)
- [sqifc](https://github.com/qif/sqifc) (?, C/C++): symbolic quantitative information flow analysis for C
- [QILURA](https://github.com/qif/jpf-qilura) (GPLv3, Java): quantifying information leaks using reliability analysis, using [Symbolic PathFinder](https://github.com/SymbolicPathFinder/jpf-symbc), z3, Omega, Latte
- [KITTeL/KoAT](https://github.com/s-falke/kittel-koat) (Apache-2.0, F\*/OCaml):
    - KITTeL: automatic termination prover for integer transition systems and imperative programs written in a fragment of Simple
    - KoAT: automatic complexity analyzer taking the same kinds of inputs as KITTeL
- [llvm2KITTeL](https://github.com/s-falke/llvm2kittel) (NCSA, C++): converter from LLVM's intermediate representation into a format that can be handled by the automatic termination prover KITTeL (UIUC)
- [TVLA](http://www.math.tau.ac.il/~tvla/) (FUSC, Java): language for expressing concrete semantics, automatic generation of abstract interpreters from concrete semantics, tunable abstractions and tunable transformers (Tel Aviv Univ.)
- [SAFE](https://www.cs.technion.ac.il/~yahave/safe/index.html) (EPL, [Java](https://github.com/tech-srl/safe)): Scalable And Flexible Error detection and verification of Java programs with respect to a set of specifications, applying static program analysis (Tel Aviv Univ.)
- [Tools](http://users.ics.aalto.fi/kepa/tools/):
    - [`boundsmodels`](http://users.ics.aalto.fi/kepa/tools/boundsmodels/) (GPLv2, C++): LTL-X model checker for 1-safe Petri nets, which generates logic programs with stable model semantics from the Petri nets. It supports step and interleaving semantics. (Helsinki Univ. of Technology)
    - [`punroll`](http://users.ics.aalto.fi/kepa/tools/punroll/) (GPLv2, C++): bounded reachability checker which generates constrained Boolean circuits from 1-bounded Petri nets. It supports process, step, and interleaving semantics. (Helsinki Univ. of Technology)
    - [`unfsmodels`](http://users.ics.aalto.fi/kepa/tools/unfsmodels/) (GPLv2, C++): LTL-X model checker with net unfoldings (Helsinki Univ. of Technology)
    - [`mcsmodels`](http://users.ics.aalto.fi/kepa/tools/mcsmodels/) (GPLv2, C++): deadlock and reachability checker using finite complete prefixes generated by the PEP tool from 1-bounded Petri nets. It uses the smodels constraint-based logic programming system as its computational engine. (Helsinki Univ. of Technology)
        - [`dlsmodels`](http://users.ics.aalto.fi/kepa/tools/dlsmodels/) (GPLv2, C++): older version of mcsmodels limited to deadlock checking only (Helsinki Univ. of Technology)
- [Smodels](http://www.tcs.hut.fi/Software/smodels/) (GPLv2, C++):  implementation of the stable model semantics for logic programs (Helsinki Univ. of Technology)
- [TASS](http://vsl.cis.udel.edu/tass/index.html) (GPLv3, C/Java): tools for the formal verification of programs used in computational science, including message-passing-based parallel programs. It uses symbolic execution and model checking techniques to verify a number of standard safety properties (such as absence of deadlocks and out-of-bound references), and can establish that two programs are functionally equivalent. (Univ. of Delaware)
- [RAPID](https://github.com/vprover/rapid) (?, C++): transforms a program and a correctness property to a FOL encoding in SMTLIB

## logic -> automata and automata tools

### LTL -> \*BA
- [ltl2ba](http://www.lsv.ens-cachan.fr/~gastin/ltl2ba/index.php): LTL -> BA (ENS de Cachan)
    - [LTL2BA4J](https://www-i2.informatik.rwth-aachen.de/Forschung/RV/ltl2ba4j/index.html) (GPL-3, Java): version of ltl2ba for Java
    - [ltl3ba](https://sourceforge.net/projects/ltl3ba/) (GPL-2, C): LTL -> BA ([Masaryk Univ.](https://is.muni.cz/th/143254/fi_r/thesis_proposal.pdf))
- [LTL -> NBA](http://www.ti.informatik.uni-kiel.de/~fritz/) (Python)
- [lbtt](http://www.tcs.hut.fi/Software/lbtt/) (GPL): tool for testing programs translating LTL -> BA
- [Wring](http://www.ist.tugraz.at/staff/bloem/wring.html) (Perl): LTL -> GBA (TU Graz)
- [Temporal Massage Parlor](http://www.bell-labs.com/project/TMP/): Optimized Translator of an Extended Linear Temporal Logic into Büchi automata and Promela (Bell Labs)
- [LBT](http://www.tcs.hut.fi/Software/maria/tools/lbt/): LTL-> BA
- [ltl2tgba](http://spot.lip6.fr/userdoc/ltl2tgba.html): LTL or PSL-> Transition-based GBA or BA (part of SPOT)
- [LTL2AUT](https://www.cs.rice.edu/CS/Verification/Software/software.html) (C++): LTL-> BA
- [DBA Minimizer](https://www.react.uni-saarland.de/tools/dbaminimizer/) (FUSC, C++): uses external SAT solver for DBA minimization
- [Wring](http://www.iaik.tugraz.at/content/research/design_verification/wring/) (Perl): translate LTL  formulae to generalized Buechi automata (TU Graz)
- [GOAL](http://goal.im.ntu.edu.tw/): graphical interactive tool for defining and manipulating Büchi automata and temporal logic formulae (NTU)
- [LTL -> Buchi Genealogy](https://spot.lip6.fr/wiki/LtlTranslationAlgorithms) ([EPITA](https://www.lrde.epita.fr/~adl/))
- [LTSA](https://www.doc.ic.ac.uk/ltsa/) (?, Java): Labelled Transition System Analyzer ([Imperial College London](http://www-dse.doc.ic.ac.uk/cgi-bin/moin.cgi/jnm))
    - [OLTSA](https://www-roc.inria.fr/arles/index.php/software/197-oltsa-ontology-based-labeled-transition-system-analyzer): ontology-based LTSA extension (INRIA)
- [WDBA](http://www.daxc.de/eth/wdba/index.html) (BSD, OCaml): Reads safety property BA and negation BA as SPIN never claims -> outputs weak deterministic BA ([ETHZ](http://www.daxc.de/eth/))
- [psl2ba](https://code.google.com/p/psl2ba/) (BSD-3, OCaml/uses CUDD): Translator from Property Specification Language (PSL) or LTL -> BA for SMV or SPIN ([ETHZ](http://www.daxc.de/eth/))
- [rltl2ba](https://github.com/juliansf/rltl2ba) (BSD, OCaml/C++/uses psl2ba, CUDD): Translator from Regular LTL (RLTL) -> BA ([IMDEA](https://software.imdea.org/~julian/))
- [aalta](http://www.lab205.org/aalta/): LTL -> BA using obligation sets (East China Normal Univ.)

### LTL -> DRA
- [ltl2dstar](https://www.ltl2dstar.de/) (GPL): LTL -> DRA (deterministic Rabin) ([Univ. Bonn](https://www.ltl2dstar.de/literature/ltl2dstar-diploma-thesis.pdf))
    - [online interface](https://www.cds.caltech.edu/~slivings/sandbox/wrapltl.php) ([Caltech.CDS](https://scottman.net/))
- [Rabinizer](https://www7.in.tum.de/~kretinsk/rabinizer3.html) (Disclaimer, Java): LTL -> DRA with generalized Rabin pairs ([TUM](https://www7.in.tum.de/~kretinsk/))
- [LTL3DRA](https://sourceforge.net/projects/ltl3dra/) (GPL-2, C): fragment of LTL -> DRA based on LTL3BA (Masaryk Univ.)

### other
- [dk.brics.automaton](https://www.brics.dk/automaton/) (BSD-3, [Java](https://github.com/cs-au-dk/dk.brics.automaton)): DFA/NFA implementation with UTF16 alphabet and support for operations on regular expressions
- [FSA function library](http://users.isr.ist.utl.pt/~pal/cadeiras/deds0708/deds/MatlabFSA.zip) (MATLAB): [doc here](http://users.isr.ist.utl.pt/~pal/cadeiras/deds0708/deds/Projects06-07/BLacerda.pdf) ([ISR-Lisbon](http://users.isr.ist.utl.pt/~blacerda/))
- [Hessen](https://forsyte.at/software/automata/) (?, C++): Automata Library (TU Wien)
- [FSME, FSMC, FSMD](https://sourceforge.net/projects/fsme/) (GPL-2, Qt): FSM editor, compiler, debugger for drawing, exports: `XML`, C++, Python
- [Kermeta](http://www.kermeta.org/) (EPL): Metamodel programming environment: editor, OCL, compiler to Java or OSGI, kermeta <-> ecore models or XMI ([IRISA](http://triskell.irisa.fr/?set_language=en&cl=en))
- [Papyrus](http://www.papyrusuml.org/scripts/home/publigen/content/templates/show.asp?L=EN&P=55&vTicker=alleza&ITEMID=3) (EPL): Graphical UML2 modeling in Eclipse ([CEA LIST](http://www-list.cea.fr/))
- [Topcased](http://www.topcased.org/) (EPL): Graphical editors for: Ecore, UML, SAM, AADL, SysML, and doc generator, model transformations (INRIA)
    - [Topcased verification tools](http://www.topcased.org/index.php?idd_projet_pere=55)
- [MARTE](http://www.omgmarte.org/): UML extension for model-driven development of real-time and embedded systems (OMG)
- [timesquare](http://timesquare.inria.fr/) (EPL): Model development kit as Eclipse plugings based on formal Clock Constraint Specification Language (CCSL) to manipulate logical time (INRIA)
- [libalf](http://libalf.informatik.rwth-aachen.de/) (LGPL-3, C++/C/Java): Learning finite-state automata: DFA: Angluin's L\*, L\* (adding counter-examples to columns), Kearns / Vazirani, Rivest / Schapire, Regular positive negative inference (RPNI), Biermann and Feldman's algorithm (using SAT-solving), and NFA: NL\*, DeLeTe2, Biermann and Feldman's (RWTH Aachen Univ., ENS Cachan, TU Munchen)
    - [AMoRE](http://amore.sourceforge.net/) (GPL-2, C/Java): Automata, Monoids, and Regular Expressions (RWTH Aaachen Univ., Univ. Kiel)
    - [libmVCA]
    - [liblangen]
    - [finite automata tool]
- [APHMIN](https://depend.cs.uni-sb.de/tools/aphmin/) (?, ?): Tools to generate, manipulate, and minimize acyclic phase-type representations (Saarland Univ.)
- [FlowSim](https://depend.cs.uni-sb.de/tools/flowsim/) (GPL-3, ?): Measure resources needed to find maximal strong simulation relation for a model under different optimizations (Saarland Univ.)
- [fc2symbmin](https://www-sop.inria.fr/meije/personnel/Michel.Bourdelles/tutorial.html#Section1): Finite State Mealy Machine analyzer (INRIA)
- [PyFMI](https://pypi.python.org/pypi/PyFMI/) (LGPL-3, Python): Load and interact with Functional Mock-Up Units ([FMU](https://www.fmi-standard.org/))
- [FMU SDK](https://github.com/mtiller/fmusdk) (?, C): FMU SDK (Qtronic)
- [hoaf](https://github.com/adl/hoaf) (?, text): Text file format for omega-automata (Masaryk Univ., EPITA, IST Austria, TU Dresden)
- [JFLAP](http://www.jflap.org/): experiment with NFA, NPA, multi-tape Turing machines
- [`ltlmp_sat`](https://github.com/nothymr/ltlmp_sat) (?, Python): LTL mean-payoff satisfiability checker
- [LtlSharp](https://github.com/ancailliau/LtlSharp) (MIT, C\#): Library for parsing and manipulating LTL formulae (U Catholique Louvain)
- [safety](https://github.com/mattmaly/safety) (?, C++): tool to translate co-safety linear temporal logic formulas into finite automata
- [RABIT and Reduce](http://languageinclusion.org/doku.php?id=tools) (?, Java):
    - RABIT (LGPL, [Java](https://github.com/ISCAS-PMC/RABIT)): checks language inclusion between Buchi automata and Nondeterministic Finite Automata (NFA), and thus also language equivalence and language universality, using generalized simulation relations, and the Ramsey method for finding counterexamples.
    - Reduce: minimizes Buchi automata, and NFA
    - [BA inclusion testing](http://languageinclusion.org/CONCUR2011/) (?, Java): Ramsey-based Buchi Automata inclusion testing
- [`automata-lib`](https://pypi.org/project/automata-lib/) (MIT, [Python](https://github.com/caleb531/automata)): library for finite automata, pushdown automata, and Turing machines, available on PyPI
- [`automata-python`](https://github.com/hemangsk/automata-python) (GPLv3, Python): library implementing finite automata, finite automata with output, pushdown automata and Turing machines
- [`python-automata`](https://code.google.com/archive/p/python-automata/) (BSD-3, [Python](https://github.com/reverie/python-automata)): library for deterministic finite automata, including simulation, negation, classical minimization, DFCA minimization, generalized cross-product, including union, intersection, and symmetric difference
- [Sage](https://doc.sagemath.org/html/en/reference/combinat/sage/combinat/finite_state_machine.html) (GPLv3, Python): finite state machines, automata, transducers
- [`python-statemachine`](https://github.com/fgmacedo/python-statemachine) (MIT, Python): package for finite state machines
- [roll-library](https://iscasmc.ios.ac.cn/roll/doku.php) (GPLv3, [Java](https://github.com/ISCAS-PMC/roll-library)): Regular Omega Language Learning, library of learning algorithms for ω-regular languages (Institute of Software Chinese Academy of Sciences)

## Term rewrite systems
- [Autowrite](https://dept-info.labri.fr/~idurand/autowrite/) (?, Lisp): check properties of term rewrite systems and manipulate tree automata
- [Timbuk](http://www.irisa.fr/celtique/genet/timbuk/) (GPL-2, OCaml): Tools for reachability proofs over term rewriting systems and manipulate bottom-up non-deterministic finite tree automata (IRISA)
- [JITty](http://wwwhome.cs.utwente.nl/~vdpol/jitty/README) (C): term rewriter with strategy annotations
- [K](http://www.kframework.org/index.php/Main_Page): rewrite-based executable semantic framework (UIUC)
- [ELAN](https://elan.loria.fr/): Rule based programming using strategic rewriting (LORIA)

## Open Systems

### Synchronous Languages
Synthesis in this context refers to compilation from source, not from temporal logic.
This distinguishes it from synthesis from temporal logic by solving games.
In some sense the latter is from an "even more declarative" problem description.

#### Imperative
- [Esterel](https://en.wikipedia.org/wiki/Esterel), [old](https://www-sop.inria.fr/meije/esterel/esterel-eng.html), [old](https://www-sop.inria.fr/esterel-org/filesv5_92/Html/Downloads/Soft/Ev592Downloads.htm): Synchronous reactive programming language and compiler to FSM (C language), Graphical symbolic debugger, explicit/BDD verification for bisimulation reduction or safety checking (Ecole des Mines de Paris, INRIA)
    - [CEC](http://www1.cs.columbia.edu/~sedwards/cec/) (BSD-3, [C++/ANTLR](https://github.com/LudvikGalois/cec-esterel)): Esterel V5 compiler to C or Verilog or BLIF ([Columbia Univ.](http://www.cs.columbia.edu/~sedwards/))
    - [scdata](https://www-sop.inria.fr/meije/esterel/scdata.html) (?): Boolean datapath generator for Esterel: translates action calls in sc code over boolean variables into standard nets also in sc (INRIA, Ecole des Mines de Paris)
    - [Ocjava](https://www-sop.inria.fr/meije/esterel/ocjava.html) (?): Esterel Java code generator (INRIA)
- [Quartz](http://rsg.cs.uni-kl.de/publications/datarsg/Schn09.pdf): derivative of Esterel that includes:
        - non-determinism
        - asynchronous execution
        - hybrid systems
    (Kaiserslautern Univ.)
    - [Averest](https://en.wikipedia.org/wiki/Averest): Synchronous programming language Quartz and compiler to TS, symbolic model checker, tool for hardware/software synthesis from Quartz ([TU Kaiserslautern](http://es.informatik.uni-kl.de/))
    - [ECL](https://sourceforge.net/projects/ecl/) (RSCPL, Java): system-level specification language for HW/SW designs and is based on Esterel and C.
The ECL compiler parses ECL, writes Esterel and C, and uses the Esterel compiler to produce an implementation. (Cadence Berkeley Labs)
- [Xeve](https://www-sop.inria.fr/meije/verification/Xeve/): Esterel verification environment (INRIA)

#### Declarative
- [Lustre](https://en.wikipedia.org/wiki/Lustre_%28programming_language%29): Declarative, synchronous dataflow programminglanguage for reactive systems
    - [Lustre](https://github.com/ladace/Lustre) (?, OCaml): Lustre interpreter
    - [Lustre-V6](https://www-verimag.imag.fr/Lustre-V6.html) (CeCILL, [OCaml](https://gricad-gitlab.univ-grenoble-alpes.fr/verimag/synchrone/lustre-v6)): the Lustre V6 compiler (Verimag)
    - [Zustre](https://github.com/coco-team/zustre) (BSD-3, Python): SMT-based PDR-style verification engine for Lustre programs, also an engine for generating assume/guarantee contracts (NASA/CMU/SEI)
    - [MATOU](http://www.cfdvs.iitb.ac.in/download/Docs/verification/tools/kronos/Verimag_Home_Page/PEOPLE/Florence.Maraninchi/MATOU/index.phtml) (?): Implementation of mode-automata on top of Lustre (VERIMAG)
        - [KIND](http://clc.cs.uiowa.edu/Kind/) (BSD-3, OCaml): K-induction based for safety properties of Lustre programs, Automatic invariant generation, parallel: PKIND (Univ. Iowa, NASA/CMU, ONERA)
    - [KIND2](https://kind2-mc.github.io/kind2/) (Apache-2, [OCaml/C++](https://github.com/kind2-mc/kind2)): Multi-engine SMT-based automatic model checker for safety properties of Lustre programs, successor of KIND (Univ. Iowa)
    - [JKind](https://loonwerks.com/tools/jkind.html) (BSD-3, [Java](https://github.com/loonwerks/jkind)): SMT-based infinite-state model checker for safety properties in Lustre, based on k-induction and property-directed reachability (Rockwell Collins)
        - [SpeAR](https://loonwerks.com/tools/spear.html) (BSD-3, [Java](https://github.com/afifarek/spear)): Specification and Analysis for Requirements tool, a frontend for writing formal specifications, translating them to Lustre, and then using the model checker JKind (Rockwell Collins, AFRL)
        - [jkind-xtext](https://github.com/agacek/jkind-xtext) (BSD-3, Java): Lustre Plug-in for Eclipse with JKind Analysis Support (Rockwell Collins)
        - [AGREE](https://loonwerks.com/tools/agree.html) (BSD-3, [Java](https://github.com/loonwerks/AGREE)): Assume Guarantee REasoning Environment, compositional, assume-guarantee-style model checker for AADL models, using k-induction (Collins Aerospace)
        - [SIMPAL](https://github.com/lgwagner/SIMPAL) (?, Java): Static IMPerative AnaLyzer, performs compositional reasoning of imperative programs written in Limp (Lustre imperative), which it translates to Lustre, and analyzes this with JKind
- [NBAC](https://pop-art.inrialpes.fr/~bjeannet/nbac/index.html) (OCaml): Co-/Reachability, slicing of synchronous deterministic reactive systems with Boolean, numerical variables (VERIMAG)
    - [`lus2nbac`](https://pop-art.inrialpes.fr/~bjeannet/nbac/index_6.html): Convert Lustre to NBAC (VERIMAG)
    - [`nbac2lucky`](https://pop-art.inrialpes.fr/~bjeannet/nbac/index_7.html): Convert counterexamples to Ludic debugger (VERIMAG)
    - [`autoc2auto`, `auto2nbac`, `nbac2auto`](https://pop-art.inrialpes.fr/~bjeannet/nbac/index_8.html):  Analyze AUTOC/AUTO hybrid automata (VERIMAG)
- [SIGNAL](https://en.wikipedia.org/wiki/SIGNAL_programming_language): Synchronized data-flow programming language for systems with multiple clocks ([INRIA](https://www.irisa.fr/espresso/home_html))
    - [Polychrony / SME](https://www.irisa.fr/espresso/Polychrony/) (GPL, Eclipse Public License): SIGNAL IDE (IRISA)
- [Sigali](https://www.irisa.fr/vertecs/Softwares/sigali.html), [old](https://www.irisa.fr/vertecs/Logiciels/sigali.html) (FUSC): Model check implicit labeled transition systems (INRIA)
- [TGV](https://www.irisa.fr/vertecs/Softwares/TGV.html) (?): Generation of conformance test suites for protocols, based on I/O transition systems (IOLTS) (IRISA)

#### Statecharts
- [PlayGo](https://www.weizmann.ac.il/mediawiki/playgo/index.php/Main_Page) (The Weizmann Institute of Science)
- [Time Rover](http://www.time-rover.com/)
- [SyncCharts](https://en.wikipedia.org/wiki/SyncCharts): Graphical formalism for reactive modeling ([Univ. Nice Sophia-Antipolis](https://www-sop.inria.fr/members/Charles.Andre/))
    - [SPORTS Project](https://www.i3s.unice.fr/~map/WEBSPORTS/SyncCharts/) (FUSC): SyncCharts tools
    - [SCC](http://julien.boucaron.free.fr/i3s/)): SyncCharts Compiler Collection for XML or BLIF or C output (Univ. Nice Sophia-Antipolis, INRIA)



# Synthesis

## Open Systems (Games: System and Uncontrolled Environment)


### Discrete games

#### GR(1) games

[GR(1)](https://dl.acm.org/citation.cfm?id=2146252) means Generalized Reactivity 1.

- [gr1c](https://github.com/tulip-control/gr1c) (BSD-3, C, uses CUDD): checking realizability of and synthesizing strategies for GR(1) specifications and much more ([Caltech.CDS](https://scottman.net/))
- [gr1py](https://github.com/slivingston/gr1py) (BSD-3, Python): an enumerative reactive synthesis tool for the GR(1) fragment of LTL (Caltech CDS, rerobots)
- [`omega`](https://github.com/tulip-control/omega) (BSD-3, Python): Specify and synthesize systems using symbolic algorithms (Caltech CDS)
- [slugs](https://github.com/LTLMoP/slugs) (BSD-3, C++, uses CUDD): a stand-alone reactive synthesis tool for GR(1) synthesis (Cornell)
- [JTLV](https://sourceforge.net/projects/jtlv/) (LGPLv2, Java/C): unified framework for the development of formal verification algorithms in Java, with GR(1) and GR(k) synthesizers, uses JavaBDD, can interface to BDD libraries in C, has parsers for SMV and FDS written using ANTLR v3 (The Weizmann Institute of Science)
    - [TLV](https://www.cs.nyu.edu/acsys/tlv/) (?, C): based on the SMV model checker, with a scripting language called TLV-Basic, users can write TLV-Basic procedures for implementing model checking or deductive verification rules, predecessor of JTLV (NYU)
        - [`synthesis.tlv`](https://www.wisdom.weizmann.ac.il/~saar/synthesis/) (?, TLV): GR(1) synthesis implemented in TLV (The Weizmann Institute of Science)
- [RATSY](https://rat.fbk.eu/ratsy/) (LGPL-2+, Python/PyGTK): PSL or BA specs -> gr1 synthesis, game-based debug approach, circuit synthesis ([TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
    - [Anzu](http://www.iaik.tugraz.at/content/research/design_verification/anzu/) (Perl, uses CUDD): synthesizes Verilog ([TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
    - [RAT](https://rat.fbk.eu/) (?, Python): RATSY's pedecessor (FBK, [TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
    - marduk (Python, needs NuSMV): game solver used by RATSY
- [NuGAT](https://es.fbk.eu/index.php?n=Tools.NuGaT) (LGPL-2+): Game solver on top NuSMV
    - [chameleon-debaets](https://code.google.com/p/chameleon-nugat-api/) (GPL-3, Java): Java interface to NuGAT
- [AspectLTL](http://aspectltl.ysaar.net/wiki/index.php?title=AspectLTL) (?, Java): Aspect programming paradigm language (The Weizmann Institute of Science)
- [open Promela](https://github.com/johnyf/openpromela) (BSD-3, Python): synthesize reactive(1) designs from multi-paradigm specifications written in an extension of Promela for open systems ([Caltech](https://www.cds.caltech.edu/~ifilippi/))

#### Full LTL games
- [Acacia+](http://lit2.ulb.ac.be/acaciaplus/) (GPL, Python/C): LTL Realizability check and winning strategy synthesis using AntiChains [repo](https://code.google.com/p/ltlsynthesis/) (Univ. Mons)
    - [Acacia](http://lit2.ulb.ac.be/acacia/) (GPL-2, Perl)
    - [Alaska](http://lit2.ulb.ac.be/alaska/) (GPL-2, Python): Antichains for Logic, Automata and Symbolic Kripke structure Analysis (predecessor of Acacia) ([ULB](https://www.ulb.ac.be/di/ssd/madewulf/))
    - [jorro](https://github.com/cloverrose/jorro) (?, Java/Perl): visualize transition systems synthesized by Acacia+ and Lily
    - [ltl2aig](https://github.com/gaperez64/acacia_ltl2aig/blob/master/ltl2aig.py) (GPL, Python): LTL -> And-inverter graph format
- [Lily](http://www.iaik.tugraz.at/content/research/design_verification/lily/) (Perl): synthesizes from PSL or LTL and I/O signal partition, works on top of Wring, outputs VERILOG or dot (TU Graz)
- [GAVS+](http://www6.in.tum.de/~chengch/gavs/) (GPL-3, Java): visualize algorithmic games used in verification and synthesis (TU Munchen)
- [Unbeast](https://www.react.uni-saarland.de/tools/unbeast/) (C++, FUSC) symbolic bounded synthesis, depends on either `ltl2ba` or `spot` (Saarland Univ.)
- [GASt](https://automata.rwth-aachen.de/research/GASt/) experimental platform:
    - NBA determinization:
        - Safra
        - Muller-Schupp
        - improved Muller-Schupp
        - Miyano/Hayashi breakpoint construction
    - game synthesis:
        - reachability
        - safety
        - weak parity
        - Staiger-Wagner
        - request-response
        - Buchi
        - generalized Buchi
        - parity
        - Muller
        - simple Streett
        - Streett
        - mean payoff
    - live sequence charts

    (RRWTH Aaachen)
- [Rabin](https://github.com/filipbartek/rabin) (?, C++): Rabin game solver ([Masaryk Univ.](https://github.com/filipbartek))
- [BoSy](https://www.react.uni-saarland.de/tools/bosy/) (Swift): Constraint-based (SAT,SMT,QBF,DQBF) bounded synthesis (Saarland Univ.)

#### Safety specs (controller synthesis)
- [AbsSynthe](https://github.com/gaperez64/AbsSynthe) (GPL-3, C/Python): controller synthesis from succinct safety specs
- [demiurge](https://www.iaik.tugraz.at/content/research/opensource/demiurge/) (GLGPL3, C++): SAT based controller synthesizer from SYNTCOMP specs (TU Graz)
- [SafetySynth](https://www.react.uni-saarland.de/tools/safetysynth/) (Swift): symbolic BDD-based safety game solver for SYNTCOMP (Saarland Univ.)
- [Reglisse](https://github.com/romainbrenguier/Reglisse) (GPL-2, OCaml): Generate hardware description from safety conditions given by regular languages

#### Parity Game solvers
- [PGSolver](http://www2.tcs.ifi.lmu.de/pgsolver/) (OCaml): tools for generating, manipulating and solving parity games (Univ. Muchich, Univ. Kassel)
- [PDSolver](https://www.cs.ox.ac.uk/matthew.hague/pdsolver.html) (OCaml): evaluating both mu-calculus formulas over pushdown systems and pushdown parity games (Oxford Univ.)
- [alpaga](http://lit2.ulb.ac.be/alpaga/) and [github](https://github.com/madewulf/alpaga) (Python, uses PyCUDD): solver parity games with imperfect information using antichains ([ULB](https://www.ulb.ac.be/di/ssd/madewulf/))
- [oink](https://github.com/trolando/oink) (Apache-2.0, C++): High-performance implementations of state-of-the-art algorithms representing different approaches to solving parity games (JKU)

#### Quantitative games
- [Quasy](https://pub.ist.ac.at/quasy/) (Scala, Java, C++): Quantitative synthesis of reactive systems from qualitative and quantitative GOAL specs, in/out: GOAL format (IST Austria)
- [GIST](https://pub.ist.ac.at/gist/index.html) (?): solving probabilistic games with ω-regular objectives qualitatively (IST Austria)
- [mpg-solver](https://github.com/gaperez64/mpg-solver) (GPL-2, C/C++/Python): Mean-payoff game solver ([Univ. Libre de Bruxelles](https://www.ulb.ac.be/di/verif/gaperez/))

#### Other
- [MLSolver](https://github.com/tcsprojects/mlsolver) (?, OCaml): solving the satisfiability and validity problems for modal fixpoint logics (Univs. Munich, Kassel)
- [`aisy`](https://bitbucket.org/art_haali/aisy-classroom) (?, Python): safety synthesis from AIGER circuits format, using PyCUDD
- [BluSTL](https://github.com/BluSTL) (BSD-3, MATLAB): BluSTL (pronounced "blue steel") is a MATLAB toolkit for automatically generating hybrid controllers from specifications written in Signal Temporal Logic.
- [G4LTL-ST](https://sourceforge.net/projects/g4ltl/) (BSD, Java): automatically generates industrial control software (supporting IEC-61131-3 Structure Text) from extended logic specifications.

### Hybrid games
- [TuLiP](https://github.com/tulip-control/tulip-control) (BSD-3, Python): Receding Horizon Temporal Logic Planning Toolbox ([Caltech.CDS](https://www.cds.caltech.edu/~murray/wiki/Main_Page))
- [LTLMoP](https://ltlmop.github.io/) (GPL-3, Python): designing, testing, and implementing hybrid controllers generated automatically from task specifications written in Structured English or Temporal Logic ([Cornell](https://cornell-asl.org/wiki/index.php?title=Main_Page))
    - [SLURP](https://github.com/PennNLP/SLURP) (GPL-3, Python): situation and language understanding robot platform, uses LTLmop (UPenn)
- [Tools from Boston Univ.](https://hyness.bu.edu/Software.html) (?, MATLAB)
- [Tools from Saarland University](https://react.cs.uni-sb.de/tools/) (Saarland Univ.)
- [Synthia](https://www.react.uni-saarland.de/tools/synthia/) (GPL-3, C/C++): Verification certificates (deductive proofs) and synthesis for partially implemented systems, abstraction refinement ([Saarland Uni.](https://www.react.uni-saarland.de/people/peter.html))
- [PESSOA](https://sites.google.com/a/cyphylab.ee.ucla.edu/pessoa/home) (FUSC, MATLAB): synthesis of correct-by-design embedded control software based on approximate bisimulations (UCLA)
- [TALIRO](https://sites.google.com/a/asu.edu/s-taliro/) (GPL, MATLAB) ([ASU](https://www.public.asu.edu/~gfaineko/))
- [SCOTS](https://gitlab.lrz.de/matthias/SCOTSv0.2) (BSD-3, C++/MATLAB): computation of discrete abstractions and symbolic controllers (TUM)
- [ARCS](https://github.com/pettni/abstr-refinement) (MIT, C/MATLAB): abstraction-refinement-based incremental synthesis for switched systems (Univ. of Michigan)

### Contracts
- [Mica](https://www.irisa.fr/s4/tools/mica/Mica__A_Modal_Interface_Compositional_Analysis_Library/Introduction.html) (CeCILL-C-1, OCaml):  Modal Interface algebra for contract based design ([INRIA/IRISA](https://www.irisa.fr/prive/Benoit.Caillaud/Benoit_Caillauds_Professional_homepage/Welcome.html))
- [OCRA](https://es-static.fbk.eu/tools/ocra/index.php?n=Main.HomePage) (closed, ?): verification of logic-based contract refinement, uses NuSMV3 (Bruno Kessler Found.)
    - [AF3-OCRA](https://es-static.fbk.eu/tools/autofocra/): OCRA plug-in for Autfocus
    - [FoReVer](https://es-static.fbk.eu/projects/forever/index.php?n=Main.Links)

### Hardware
- [Yosys](https://github.com/cliffordwolf/yosys) (ISC, C++): a framework for RTL synthesis tools
- [Clash](https://www.clash-lang.org/) (?, Haskell) generates VHDL from Haskell
- [Lava](https://ku-fpg.github.io/software/kansas-lava) (BSD-3, [Haskell](https://github.com/ku-fpg/kansas-lava)): generates circuits from FSMs, behavioural specifications (VHDL, Verilog), and verification via NuSMV (University of Kansas)
- [Chisel](https://github.com/ucb-bar/chisel/) (?, Scala): supports advanced hardware design using highly parameterized generators and layered domain-specific hardware languages; Chisel can generate a high-speed C++-based cycle-accurate software simulator, or low-level Verilog designed to pass on to standard ASIC or FPGA tools for synthesis and place and route

### Other
- [Times](http://www.timestool.com/) (?): Tool for Modeling and Implementation of Embedded Systems (GUI editor, simulator, verifier for schedulability analysis) (Uppsala Univ.)
- [BigMC](https://github.com/bigmc/bigmc) (GPL, C++/C/PHP/...): Bigraphical reactive systems (IT Univ. Copenhagen)
- [Ticc](https://code.google.com/p/ticc/) (GPL-2, ?): Interface compatibility and composition, components specify own behavior and that expected by others, CTL properties checked and propagated (UCSC)



# Timed Systems
- [UPPAAL](https://www.uppaal.org/), [UPPAAL-Tiga](https://people.cs.aau.dk/~adavid/tiga/) (FUSC): Timed automata (Uppsala Univ., Aalborg Univ.)
    - [manipulate UPPAAL XML](https://launchpad.net/pyuppaal) (GPL-3, Python)
    - [Yggdrasil](http://www.quasimodo.aau.dk/tools.html) (?, ?): UML (subset) -> Uppaal, intended for test generation (Aalborg Univ.)
    - [METAMOC](http://metamoc.dk/) (GPL-3, Python): WCET Analysis of ARM Processors using Real-Time model-checking (Aalborg Univ.)
    - [SARTS](http://www.sarts.dk/old.php) (?, Java): Model Based Schedulability Analysis of Real-Time Systems, SCJ2, UPPAAL (Aalborg Univ.)
    - [UPPAAL DBM Library](https://people.cs.aau.dk/~adavid/UDBM/) (GPLv2, C++): efficient data structures to represent clock constraints in timed automata (Aalborg Univ.)
        - [Python bindings](https://people.cs.aau.dk/~adavid/UDBM/python.html) (GPLv3, Python/SWIG/C): to UPPAAL (Aalborg Univ.)
        - [Ruby bindings](https://people.cs.aau.dk/~adavid/UDBM/ruby.html) (GPLv2, Ruby/C++): to UPPAAL (Aalborg Univ.)
        - [`udbml`](https://github.com/osankur/udbml) (AGPL-3, C++/OCaml): OCaml wrapper for the UPPAAL DBM library
- [OPAAL](https://launchpad.net/opaal) (GPL-3, Python): distributed/parallel (discrete time) model checker for networks of timed automata  using MPI
- [ECDAR](https://people.cs.aau.dk/~adavid/ecdar/) (FUSC): timed interface theory (Aalborg, INRIA, ITU)
- [PyECDAR](https://project.inria.fr/pyecdar/) (GPL-2, Python): solve timed games based on timed automata models (ITU)
- [IOA](https://groups.csail.mit.edu/tds/ioa/) (MIT, Java): I/O automata formal language (MIT)
- [TEMPO](http://www.veromodo.com/) (closed, Java): Formal language for modeling distributed systems with or without timing constraints as collections of interacting state machines, i.e., timed input/output automata (TIOA) (UIUC)
    - [Tempo2HSal](http://www.csl.sri.com/users/tiwari/VVFCS.html) (?, Python): Tempo (`.tioa`) -> HybridSAL (`.hsal`) translator (SRI)
- [ATAS](https://sourceforge.net/projects/atao/) (GPL-3, Python): Alternating 1-clock (fully decidable) Timed Automata Solver
- [PPL binding](https://launchpad.net/pyppl) (GPL-2, Python): for [Parma Polyhedral Lib](http://bugseng.com/products/ppl) features some specific methods for Timed Automata analysis
- [MCPTA](https://www.modestchecker.net/) (FUSC, ?): Probabilistic Timed Automata model checker for MoDeST, UPPAAL, PRISM - maps on PRISM (Saarland Univ.)
- [SAAtRE](http://symbolaris.com/info/saatre.html) (?): Abstraction refinement model checker for Timed Automata based on extended SAT-solving, UPPAAL-like input format (Univ. Oldenburg, CWI)
- [Fortuna](https://www.cs.ru.nl/J.Berendsen/fortuna/) (GPL-3, C++/Eclipse): MC priced probabilistic timed automata (PPTAs) (Univ. Twente)
- [COSPAN](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.39.8153) (?, ?): Automata-theoretic verification of coordinating processes with timing constraints (UPenn)
- [Romeo](http://romeo.rts-software.org/?page_id=2): timed Petri nets (IRCCyN)
- [ExSched](http://www.idt.mdh.se/~exsched/): develop operating system schedulers for VxWorks and Linux w/o modifying the underlying kernel ([Malardalen Univ.]http://www.es.mdh.se/staff/197-Mikael__sberg))
- [RTComposer](http://www.cs.bgu.ac.il/~geraw/rtcomposer.html) (Java): classes and utilities for predictable real-time scheduling (BenGurion, UPenn)
- [ASTRAL](http://dimacs.rutgers.edu/Workshops/Security/program2/kemmerer/index.html): MC of real-time systems (UCSB)
- [PAT](http://pat.sce.ntu.edu.sg/?page_id=2602) (?, C\#): simulator, MC, refinement checker for concurrent and RT systems (Nanyang Tech. Univ.)
- [HCMC](http://www.lsv.ens-cachan.fr/~fl/cmcweb.html) (? , C++): Compositional model checking for real-time systems (ENS-Cachan)
- [IMITATOR](https://www.imitator.fr) (GPLv3, [OCaml/Python](https://github.com/imitator-model-checker/imitator/)): is a tool for parametric verification and robustness analysis of real-time systems. It relies on the formalism of networks of parametric timed automata, augmented with integer variables and stopwatches (LORIA, Univ. de Lorraine, Inria, CNRS, LIPN, LSV, Sorbonne Univ., Univ. Pierre et Marie Curie, ENS Cachan, Aarhus Univ.)
- [CoVerTS](https://github.com/astefano/CoVerTS) (Scala): compositional verification of state properties for timed systems

# Hybrid Systems
- [Ptolemy](https://ptolemy.eecs.berkeley.edu/index.htm) (BSD-3, Java): modeling, simulation, and design of concurrent, real-time, embedded systems (UC Berkeley)
- [HyLink](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HyLink) (FUSC, Python): Restricted Simulink/Stateflow models -> HyXML-> HyTech or UPPAAL (UIUC)
- [CHARON](https://rtg.cis.upenn.edu/mobies/charon/) (?, Java): Language and implementation (editor, model browser, visual simulator) for modular specification of interacting hybrid systems based on the notions of agent and mode (UPenn)
- [CARTS](https://rtg.cis.upenn.edu/carts/) (FUSC, Java): Compositional Analysis of Real-Time Systems (UPenn)
- [START](http://www.andrew.cmu.edu/user/arieg/Rek/): time-bounded static analysis of concurrency properties of Real-Time Embedded Software
- [IF](https://www-verimag.imag.fr/~async/IF/index.html) (FUSC): static analysis, model-checking, test generation, [Open-Kronos](https://www-verimag.imag.fr/~tripakis/openkronos.html), [Kronos](https://www-verimag.imag.fr/DIST-TOOLS/TEMPO/kronos/): TCTL verification of Timed Automata (VERIMAG)
- [CIF](https://cif.se.wtb.tue.nl/): Compositional Interchange Format for Hybrid Systems toolset
- [Passel](https://publish.illinois.edu/passel-tool/) (closed, C\#/Python): invariant synthesis and inductive invariant proving (UIUC)
- [Rabbit](https://www.sosy-lab.org/~dbeyer/Rabbit/) (Apache): RTS modular spec: timed (and hybrid) automata: CottbusTimed Automata, MC for reachability analysis and refinement check (Bradenburg TU)
- [Mobius](https://www.mobius.illinois.edu/) (?, Java/C++): Model-based environment for validation of system reliability, availability, security, and performance ([UIUC](https://www.perform.csl.illinois.edu/))
- [HYMITATOR](GLP, OCaml) (https://lipn.univ-paris13.fr/~andre/software/hymitator/):  is a tool dedicated to the synthesis of parameters for hybrid automata

## Linear
- [HyTech](https://embedded.eecs.berkeley.edu/research/hytech/) (FUSC, C): computes condition under which a linear hybrid system satisfies a temporal requirement (UC Berkeley)
- [d/dt](https://www-verimag.imag.fr/~tdang/ddt.html) (?, ?): Reachability analysis of Continuous and Hybrid Systems with linear differential inclusions ([VERIMAG](https://www-verimag.imag.fr/~tdang/))
- [HARE](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HARE) (?): Abstraction refinement for safety
- [PHAVer](https://www-verimag.imag.fr/~frehse/phaver_web/) (GPL-2, C++): verifying safety properies of hybrid systems (exact arithmetic, on-the-fly over-approximation of PWA dynamics, compositional and assume-guarantee reasoning) ([Verimag](https://sites.google.com/site/frehseg/))
    - [vim highlight](https://www.vim.org/scripts/script.php?script_id=3256), its [github](https://github.com/vim-scripts/phaver)
    - [ProHVer](https://depend.cs.uni-sb.de/tools/prohver/) (GPL-3, C++): Unbounded reachability probability for probabilistic hybrid automata (Univ. Saarland)
- [CheckMate](https://www.mathworks.com/matlabcentral/fx_files/15441/3/content/doc/main.htm) (MATLAB) modeling, simulation and investigation, [demos](https://www.mathworks.com/matlabcentral/fileexchange/17004-checkmate-demos)
- [HYSDEL](http://control.ee.ethz.ch/~hybrid/hysdel/) (GPL, C++/MATLAB): (Hybrid Systems Description Language) HYSDEL -> MLD compiler, also language to model interconnected linear systems and automata (ETHZ)
- [Hybrid Toolbox for MATLAB](http://cse.lab.imtlucca.it/~bemporad/hybrid/toolbox/) (FUSC, MATLAB/Simulink): Modeling, simulation, verification, constrained MPC, generate linear and hybrid MPC PWA control laws ([IMT Lucca](http://cse.lab.imtlucca.it/~bemporad/Alberto_Bemporads_Home_Page/Home_Page.html))
- [Ellipsoidal Toolbox for MATLAB](https://code.google.com/p/ellipsoids/) (BSD-3, MATLAB): External and internal ellipsoidal approximations of geometric (Minkowski) sums and differences of ellipsoids, intersections of ellipsoids and intersections of ellipsoids with halfspaces and polytopes; distances between ellipsoids, between ellipsoids and hyperplanes, between ellipsoids and polytopes; and projections onto given subspaces. For forward and backward reach sets of continuous- and discrete-time PWA systems (UC Berkeley)
- [MATISSE](http://www-ljk.imag.fr/membres/Antoine.Girard/Software/Matisse/) (GPL-3, MATLAB): Approximate bisimulations: safety verification and reachable set computation of large dimensional, constrained linear systems. Needs: MPT, YALMIP, SEDUMI (UPenn, IMAG)
- [BACH](http://seg.nju.edu.cn/BACH/): bounded model checker for Linear Hybrid Systems (Nanjing Univ.)
- [`tltk-mtl`](https://pypi.org/project/tltk-mtl) (?, Python): tool for computing Metric Temporal logic robustness

## Non-Linear
- [HTV](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HTV) (closed, MATLAB): verify systems from their simulation and run-time traces using imprecise samples and possibly incomplete models to compute overapproximations of bounded reach sets (UIUC)
- [SpaceEx](http://spaceex.imag.fr/) (GPL-3, C++): Reachability and safety verification (Verimag, Lab Jean Kuntzmann, DGA-MI)
- [Ariadne](http://trac.parades.rm.cnr.it/ariadne/) (GPL-3, C++/Python): Dynamical systems set-based analysis (reachability analysis, robust simulation, safety verification - reset, flow, guard predicates given by nonlinear functions) (Univ. Udine, PARADES, CWI, Univ. Verona)
- [MPT](http://control.ee.ethz.ch/~mpt/2/about.php) (GPL, MATLAB): Design, analysis and deployment of optimal controllers for constrained linear, nonlinear and hybrid systems (ETHZ)
- [HybridSal](http://sal.csl.sri.com/hybridsal/) (GPLv2, [Java/Python](https://github.com/SRI-CSL/HybridSal)): Language extension to SAL for specifying Hybrid Systems and hybrid abstraction tool to discrete SAL specifications for model checking with other SAL tools ([SRI](http://www.csl.sri.com/users/tiwari/))
    - [Relational Abstraction](http://www.csl.sri.com/users/tiwari/relational-abstraction/) (GPL-2, LISP): creating relational abstractions of HybridSAL models (SRI)
    - `hsal2xml` (GPL-2, Java): `HybridSAL` -> `XML`
- [NLToolbox](https://www-verimag.imag.fr/~tdang/NLTOOLBOX/) (u, C/C++): Non-linear dynamical system reachability: polynomial using Bernstein expansion, more general using hybridization ([VERIMAG](https://www-verimag.imag.fr/~tdang/))
- [Flow\*](http://systems.cs.colorado.edu/research/cyberphysical/taylormodels/) (GPL-3, C++): Over-approximation Taylor model flowpipes: polynomial ODEs, polynomial invariants, guards, resets (RWTH Aaachen, Univ. Colorado Boulder)
- [HSolver](http://hsolver.sourceforge.net/) (LGPL): based on RSOLVER constraint solver, correctness does not depend on floating point rounding errors, handles non-linear ODEs ([Academy of Sciences Czech Republic](http://www2.cs.cas.cz/~ratschan/))
- [AMC](http://symbolaris.com/info/amc.html) (?, Mathematica): model checker for non-linear hybrid systems based on the abstraction refinement framework (CMU, Univ. Oldenburg)
- [pyHybridAnalysis](http://www.dmi.units.it/~casagran/pyHybridAnalysis/) (LGPL-3, Python): ε-semantics reachability ([VERIMAG](https://www-verimag.imag.fr/~dreossi/publications.html), Udine Univ., Trieste Univ.)
- [LtlOpt](https://www.cds.caltech.edu/~ewolff/ltlopt.html) (BSD-3, MATLAB): optimal control of high-dimensional, nonlinear systems using LTL specs ([Caltech](https://www.cds.caltech.edu/~ewolff))
- [reasys](https://github.com/jadecastro/reasyns) (BSD-3, MATLAB): Reactive synthesis for nonlinear systems ([Cornell, Toyota](https://jadecastro.github.io))
- [c2e2](https://publish.illinois.edu/c2e2-tool/) (?, Assembly): tool for verifying bounded-time invariant properties of Stateflow models (UIUC)
- [HyST](http://verivital.com/hyst/) (LGPLv3, Java / Python / Matlab): transformation and semantics-preserving translation (to Flow\*, dReach, HyComp, HyCreate) of hybrid automata networks from SpaceEx format ([AFRL](http://stanleybak.com/), [IST](https://www.sergiybogomolov.com/), [UTA](http://www.taylortjohnson.com/))
- [VeriSiMPL](https://sourceforge.net/projects/verisimpl/) (GPLv3, C++): constructs finite abstractions of autonomous Max-Plus-Linear (MPL) systems over R^n, as finite-state Labeled Transition Systems (LTS), exported to the NuSMV language for verification using NuSMV
- [HyCOMP](https://es-static.fbk.eu/tools/hycomp/) (FUSC, ?): model checker for asynchronous hybrid systems, built on top of the nuXmv model checker, and of the Mathsat5 SMT solver (FBK)

## Stochastic
- [MoToR](https://depend.cs.uni-sb.de) (GPL, ?): Macro-preprocessor for MoDeST, a stochastic real-time systems formalism, interfacing to UPPAAL, CADP, Eclipse, Mobius (Univ. Saarlandes)
    - [Eclipse plugin](https://depend.cs.uni-sb.de/index.php?446) (Univ. Saarlandes)
- [MRMC](http://www.mrmc-tool.org/trac/) (GPL-3, C): MC for: Discrete/Continuous Markov Chains, Reward models, decision processes (Univ. Twente, RWTH Aachen)
- [PASS](https://depend.cs.uni-sb.de/tools/pass/) (bin, ?): CEGAR MC for infinite-state probabilistic models, MDPs (Saarland Univ.)
- [INFAMY](https://depend.cs.uni-sb.de/tools/infamy/) (bin, ?): CSL Model Checker for infinite-state Markov chains - CTMCs (Saarland Univ.)
- [PARAM](https://depend.cs.uni-sb.de/tools/param/) (GPL-3, C++): Reachability probability computation for parametric Markov chains - DTMCs (Saarland Univ.)

# Theorem Provers
- [TLAPS](https://tla.msr-inria.inria.fr/tlaps) (BSD-2, [OCaml/Isabelle](https://github.com/tlaplus/tlapm)): Theorem prover for TLA+ using: Isabelle, ls4, Zenon, Z3 (INRIA/MSR)
    - [`pf2`](https://research.microsoft.com/en-us/um/people/lamport/latex/latex.html) (LaTeX): package for writing structured proofs of the form described in ["How to write a 21st century proof"](https://research.microsoft.com/en-us/um/people/lamport/pubs/proof.pdf)
    - [`pfnum`](https://research.microsoft.com/en-us/um/people/lamport/latex/pfnum.html) (C): Rewrites structured proofs in a LaTeX file to renumber proofs steps as they will appear after typesetting
    - [`pf2html`](https://sourceforge.net/projects/pf2html/) [home](https://www.dbai.tuwien.ac.at/proj/pf2html/index.html) (GPL-2, Perl): adds functionality to LATEX2HTML such that LATEX documents written with pf.sty can be viewed in a web browser up to the desired level of detail for each branch of a structured proof (TU Wien)
    - [`hyperpf`](https://research.microsoft.com/en-us/um/people/lamport/proofs/hyperpf.html) (C): HyperTeXt structured proof reader
    - [Verifying TLA+ invariants using ACL2](https://people.csail.mit.edu/cpacheco/publications/verifying-tla-abstract.html) (UT Austin)
- [Isabelle](https://www.cl.cam.ac.uk/research/hvg/Isabelle/) (BSD-3, [ML/Scala/Isabelle](https://github.com/isabelle-prover/mirror-isabelle), [mirror](https://github.com/seL4/isabelle)): (Univ. Cambridge, TU Munchen, Univ. Paris-Sud)
    - [Isabelle/TLA](https://homepages.loria.fr/SMerz/projects/isabelle-tla/) [github](https://github.com/seL4/isabelle/tree/master/src/HOL/TLA): encoding of Lamport's TLA in Isabelle, ships with Isabelle's standard distribution ([INRIA](https://members.loria.fr/SMerz/index.html))
    - [AFP](https://www.isa-afp.org/): Archive of Formal Proofs
    - [Isabelle/eclipse](https://andriusvelykis.github.io/isabelle-eclipse/) (EPL-1.0, [Python/Scala](https://github.com/andriusvelykis/isabelle-eclipse)): Eclipse integration for the Isabelle proof assistant
    - [VHDL semantics](https://github.com/rizaldialbert/vhdl-semantics) (BSD-2, Isabelle): formalization of the language VHDL in the Isabelle theorem prover (Nanyang Technological Univ.)
    - [PSL](https://github.com/data61/PSL) (CSIRO, Isabelle/ML): implementation of proof strategy language (PSL) and its default strategy, for Isabelle (CSIRO)
    - [`ismt`](http://www.galois.com/files/open_source/ismt/) (BSD-3, Isabelle/ML): integration of Yices SMT solver in Isabelle/HOL (Galois Inc.)
    - [IsaFol](https://bitbucket.org/isafol/isafol/wiki/Home) (?, Isabelle): a repository of formalizations of logical calculi and related topics, such as DPLL, CDCL, and resolution
    - [IsaFoR](http://cl-informatik.uibk.ac.at/software/ceta/) (LGPLv3, [Isabelle](http://cl2-informatik.uibk.ac.at/rewriting/mercurial.cgi/IsaFoR)): Isabelle/HOL formalization of rewriting for certified tool assertions
    - [CeTA](http://cl-informatik.uibk.ac.at/software/ceta/) (LGPLv3, [Haskell](http://cl2-informatik.uibk.ac.at/rewriting/mercurial.cgi/IsaFoR): tool that certifies (non)termination or (non)confluence or completion or complexity proofs provided by some automated tool
- [HOL](https://hol-theorem-prover.org) (BSD-3/Open Source, [ML](https://github.com/HOL-Theorem-Prover/HOL)): Interative Theorem proving in higher-order logic ([Univ. Cambridge](https://www.cl.cam.ac.uk/research/hvg/HOL/))
    - [Holfoot](http://holfoot.heap-of-problems.org/) (BSD, [ML](https://github.com/HOL-Theorem-Prover/HOL/tree/develop/examples/separationLogic/src)): Implementation of Smallfoot inside of HOL 4
    - [HOLBDDlib](https://www.cl.cam.ac.uk/~mjcg/HolBddLib/) (BSD-3, [ML](https://github.com/HOL-Theorem-Prover/HOL/tree/develop/examples/HolBdd)): kernel of representation judgement rules as infrastructure for building fully-expansive combinations of HOL theorem proving and BDD-based symbolic calculation algorithms, uses the BuDDy BDD package
- [HOL Light](https://www.cl.cam.ac.uk/~jrh13/hol-light/) (BSD-2, [OCaml](https://github.com/jrh13/hol-light)): Interactive Theorem Proving in higher-order logic (Cambridge Univ., AWS)
- [HOL Zero](http://www.proof-technologies.com/holzero/index.html) (BSD, OCaml): Basic theorem prover for the HOL logic for checking and/or consolidating proofs created on other theorem provers, and a pedagogical example
    - [HOL Zero](https://github.com/domasin/NHolZ/) (BSD, F#): port to F\#
- [HOL-Omega](http://trustworthytools.com/id17.html) (BSD-3, [ML](https://github.com/HOL-Theorem-Prover/HOL/tree/HOL-Omega): Merging of HOL4, HOL2P by Völker, and major aspects of System Fω from chapter 30 of Types and Programming Languages by Pierce, implements a new logic, which is an extension of the existing higher order logic of the HOL4 system
- [Coq](https://coq.inria.fr/) (LGPL-2.1, [OCaml](https://github.com/coq/coq)): formal proof management system. It provides a formal language to write mathematical definitions, executable algorithms and theorems together with an environment for semi-interactive development of machine-checked proofs. (INRIA, Ecole Polytechnique, Paris-Sud 11 Univ., Paris Diderot Univ., CNRS)
    - Vim:
        - [Coqtail](https://github.com/whonore/Coqtail) (MIT, Python/Vim script): interactive Coq Proofs in Vim
        - [Coquille](https://github.com/the-lambda-church/coquille) (ISC, Vim script/Python): interactive theorem proving with Coq in vim
    - IDE:
        - [JsCoq](https://jscoq.github.io) (several, [JavaScript](https://github.com/jscoq/jscoq)): online Integrated Development Environment for the Coq proof assistant that runs in a browser (MINES ParisTech)
        - [`coq_jupyter`](https://github.com/EugeneLoy/coq_jupyter) (Apache-2.0, Python/JavaScript): Jupyter kernel for Coq, [try it online](https://mybinder.org/v2/gh/EugeneLoy/coq_jupyter_demo/master?filepath=demo.ipynb)
        - [VsCoq](https://github.com/coq-community/vscoq) (MIT, TypeScript): Visual Studio Code extension for Coq
    - Libraries:
        - [HoTT library](https://github.com/HoTT/HoTT) (BSD-2, Coq): a formalization of homotopy type theory in the Coq proof assistant
        - [UniMath](https://github.com/UniMath/UniMath) (FOSS, Coq): a library that aims to formalize a substantial body of mathematics using the univalent point of view.
        - [Coq-Polyhedra](https://github.com/Coq-Polyhedra/Coq-Polyhedra) (CeCILL-B, Coq): Formalizing convex polyhedra in Coq ([INRIA/École Polytechnique](http://www.cmap.polytechnique.fr/~allamigeon/))
        - [ControlHTT](https://github.com/jpaykin/ControlHTT) (?, Coq): an adaptation of Hoare Type Theory for control software (Galois Inc.)
        - [Categories](https://github.com/amintimany/Categories) (?, Coq): a formalization of category theory in the Coq proof assistant (Aarhus Univ.)
        - [fourcolor](https://github.com/math-comp/fourcolor) (?, Coq): formalization of the four-color theorem
        - [odd-order](https://github.com/math-comp/odd-order) (?, Coq): formal proof of the odd-order theorem
        - [infotheo](https://github.com/affeldt-aist/infotheo) (LGPL-2.1): formalization of information theory and linear error-correcting codes
        - [proofs](https://github.com/stepchowfun/proofs) (MIT, Coq): a selection of formal proofs in Coq (Google)
        - [GeoCoq](https://github.com/GeoCoq/GeoCoq) (LGPL-3.0, Coq): formalization of geometry in Coq, based on [Tarski's](https://en.wikipedia.org/wiki/Alfred_Tarski) [axiom system](https://en.wikipedia.org/wiki/Tarski%27s_axioms)
    - Embeddings:
        - [TLA^{Coq}](https://github.com/philipjf/AWG-AVOCS-2016) (?, Coq): Deep embedding of TLA in Coq (Univ. of Oregon, Sandia)
    - Tools:
        - [Ynot](https://ynot.cs.harvard.edu) (BSD-3, [Coq/OCaml](https://github.com/ynot-harvard/ynot)): library for the Coq proof assistant which turns it into a full-fledged environment for writing and verifying imperative programs (Harvard Univ.)
        - [verdi](https://github.com/uwplse/verdi) (BSD-2, Coq): framework for formally verifying distributed systems implementations in Coq
        - [`coq-lit`](https://github.com/wilcoxjay/coq-lit) (?, Python): script that processes special commands inside comments in Coq source files to produce Markdown and raw HTML that generates a blog post (Univ. of Washington)
        - [CompCert](https://compcert.org) (FUSC, [Coq/OCaml](https://github.com/AbsInt/CompCert)): a formally-verified compiler for a large subset of the C programming language that generates code for the PowerPC, ARM, x86 and RISC-V processors, the compiler has been verified in Coq (Inria)
        - [SMTCoq](https://github.com/smtcoq/smtcoq) (CeCILL-C, Coq/OCaml): a Coq plugin that checks proof witnesses coming from the external SAT and SMT solvers ZChaff, CVC4, veriT, and decision procedures that discharge Coq goals to these solvers
- [PVS](https://pvs.csl.sri.com/) (GPL-3, [Common LISP/C/Emacs LISP/others](https://github.com/SRI-CSL/PVS)): Specification language and theorem prover, based on Church's type theory extended with dependent types (SRI CSL)
    - [NASA PVS Library](https://github.com/nasa/pvslib) (Various, Python/Lisp): Collection of formal PVS developments ([NASA Langley](https://shemesh.larc.nasa.gov/fm/))
    - [Invariant-Checker](https://www-verimag.imag.fr/~graf/INVARIANT-CHECKER/): predicate abstraction and verification of invariance reactive properties using theorem-proving and MC, front to PVS ([IMAG](https://www-verimag.imag.fr/~graf/))
    - [PVSPackrat](https://github.com/SRI-CSL/PVSPackrat) (?, PVS): PVS proofs for PEG grammars and Packrat parsers (SRI CSL)
- [Lean](https://github.com/leanprover/) (Apache-2, C++/Python): Theorem prover ([Microsoft Research](https://leodemoura.github.io/))
    - [mathlib](https://github.com/leanprover-community/mathlib/) (Apache-2.0, Lean): library of mathematics and programming infrastructure for Lean
    - [lean-ga](https://github.com/pygae/lean-ga) (MIT, Lean): formalization of geometric algebra in Lean
    - [Spectral](https://github.com/cmu-phil/Spectral) (Apache-2.0, Lean): Formalization of the Serre spectral sequence in Lean 2.
- [Zenon](http://zenon-prover.org) (BSD-3, [OCaml](https://github.com/zenon-prover/zenon)): FOL with equality based on tableau, reads Coq, Focal, TPTP, Zenon, and generates Coq, Isar (and in other formats) proofs, includes TLA+ theory extension [OPAM](https://opam.ocaml.org/packages/zenon/) (INRIA)
    - [Zenon arith](https://www.rocq.inria.fr/deducteam/ZenonArith/index.html) (BSD-3, OCaml): extension to handle linear arithmetic (INRIA)
    - [Zenon modulo](https://deducteam.gitlabpages.inria.fr/zenonmodulo/) (BSD-3, [OCaml](https://github.com/Deducteam/zenon_modulo): extension to deduction modulo (INRIA)
    - [Super Zenon](http://cedric.cnam.fr/~delahaye/super-zenon/) (?, ?): extension using superdeduction (CEDRIC/CNAM, Siemens IC-MOL)
- [AIMA `logic.py`](https://github.com/aimacode/aima-python/blob/master/logic.py) (MIT, Python): Artificial Intelligence - A Modern Approach: Representations and Inference for Logic (UC Berkeley, Google)
- [Nunchaku](https://github.com/nunchaku-inria/nunchaku) (BSD-2, OCaml): A counter-example finder for higher-order logic, designed to be used from various proof assistants (INRIA)
- [Nitpick](https://github.com/seL4/isabelle/blob/e3f58c3db416e00ee7e4280c8c50522b222d7c5e/src/HOL/Nitpick.thy) (BSD-3, Isabelle): Counterexample generator for Isabelle/HOL
- [Walnut](https://github.com/hamoonmousavi/Walnut) (GPLv3, Java): Automated Theorem Prover for Automatic Words
- [Phox](https://raffalli.eu/phox/) (LGPL-3.0, [OCaml](https://github.com/craff/phox)): Proof assistant based on High Order logic which is eXtensible (Université de Savoie)
- [Dedukti](https://deducteam.github.io) (CecILL-B, [OCaml](https://github.com/Deducteam/Dedukti)): Implementation of the λΠ-calculus modulo rewriting
    - [Dedukti libraries](https://github.com/Deducteam/Libraries) (?, Dedukti): A collection of hand-written files for Dedukti
    - [Lamdapi](https://github.com/Deducteam/lambdapi) (CeCILL-2.1, OCaml): Proof assistant based on the λΠ-calculus modulo rewriting, mostly compatible with the proof checker Dedukti
- [Automath](https://en.wikipedia.org/wiki/Automath) (?, ?): One of the first formal proof languages and proof checker ([Eindhoven Univ.](https://en.wikipedia.org/wiki/Nicolaas_Govert_de_Bruijn))
    - [Modern Automath implementation](https://www.cs.ru.nl/~freek/aut/) (?, C): Languages AUT-68, AUT-QE ([Radboud Univ. Nijmegen](https://www.cs.ru.nl/~freek/index.html))
- [TPS](https://gtps.math.cmu.edu/tps.html): (CMU)
- [ALF](https://www.cse.chalmers.se/research/group/logic/alf/guide.html) (Univ. Goterborg/Chalmers)
- [Alfa](https://www.cse.chalmers.se/~hallgren/Alfa/): successor of ALF
- [Agda](https://wiki.portal.chalmers.se/agda/pmwiki.php) (MIT and BSD-2, [Haskell](https://github.com/agda/agda/)): An interactive system for writing and checking proofs, based on intuitionistic type theory. A dependently typed functional programming language.
    - [HoTT-Agda](https://github.com/HoTT/HoTT-Agda) (MIT, Agda): A library of homotopy type theory and univalent foundations
- [Cedille](https://cedille.github.io/) (MIT, Agda/Haskell):
    interactive theorem-prover and dependently typed programming language,
    based on extrinsic (aka Curry-style) type theory
- [ACL2](https://www.cs.utexas.edu/users/moore/acl2/) (BSD-3, [Lisp](https://github.com/acl2/acl2)):  logic and programming language in which you can model computer systems, together with a tool to help you prove properties of those models. "ACL2" denotes "A Computational Logic for Applicative Common Lisp", part of Boyer-Moore family of provers (Univ. Texas at Austin)
    - [Nqthm](https://en.wikipedia.org/wiki/Nqthm) (GPL-2, ?): Boyer–Moore TP using Pure LISP variant, precursor to ACL2 (Univ. Texas, Austin)
    - [Milawa](https://www.cs.utexas.edu/users/moore/acl2/manuals/current/manual/index-seo.php/ACL2____MILAWA?path=3524/3584/475) (MIT, [Lisp](https://github.com/acl2/acl2/tree/master/books/projects/milawa)): "Self-verifying" theorem prover for an ACL2-like logic (UT Austin)
    - [Jitawa](https://www.cl.cam.ac.uk/~mom22/jitawa/) (?, Lisp): Verified Lisp runtime that hosts Milawa and ensures its soundness, as formally proved (Cambridge Univ.)
    - [ivy](https://www.cs.unm.edu/~mccune/papers/ivy/) (BSD-3, [Lisp](https://github.com/acl2/acl2/tree/master/books/workshops/1999/ivy)): Preprocessor and proof checker for resolution/paramodulation theorem provers, coded in ACL2 and proved sound for finite interpretations ([Univ. of New Mexico](https://www.cs.unm.edu/~mccune/))
- [INKA5](https://www.dfki.de/vse/systems/inka/inka5.html), [INKA](https://www.dfki.de/vse/systems/inka/): Inductive Theorem Prover
- [Otter and Mace2](https://www.cs.unm.edu/~mccune/otter/): first-order and equational logic
- [Prover9 and Mace4](https://www.cs.unm.edu/~mccune/prover9/): Successors of Otter and Mace2
- [EQP](https://www.cs.unm.edu/~mccune/eqp/): first-order equational logic: associative-commutative unification and matching, a variety of strategies for equational reasoning, and fast search
- [TWELF](http://twelf.org/wiki/Main_Page) (BSD-2, ML): a language used to specify, implement, and prove properties of deductive systems such as programming languages and logics
- [Maude](https://maude.cs.illinois.edu) (GPLv2, ?): high-performance reflective language and system supporting both equational and rewriting logic specification and programming for a wide range of applications, with [tools](https://maude.cs.illinois.edu/w/index.php/Maude_Tools) (UIUC)
    - [Maude ITP](https://maude.cs.uiuc.edu/tools/itp/): Inductive Theorem Prover
    - [C-Reducer](http://sysma.lab.imtlucca.it/tools/c-reducer/): Automatic c-reduction of object based modules for the Maude system (IMT Lucca)
    - [MESSI](http://sysma.lab.imtlucca.it/tools/ensembles/): Design, validation and performance evaluation of self-assembly strategies with Maude (IMT Lucca)
    - [Circ](https://fsl.cs.illinois.edu/index.php/Circ):  automated behavioral prover based on the circularity principle for Maude ([UIUC](https://fsl.cs.illinois.edu/index.php/Main_Page))
    - [LTLR](https://maude.cs.uiuc.edu/tools/tlr/): LTL rewriting model checker within Maude (UIUC)
    - [IMaude](https://github.com/SRI-CSL/imaude) (?, NewLisp/Maude/C/Python): Interactive Maude (SRI CSL)
- [LP: Larch Prover](http://www.sds.lcs.mit.edu/spd/larch/LP/overview.html) (?): Multisorted first-order logic, interactive (MIT)
    - [Larch Shared Language (LSL) Checker](http://www.sds.lcs.mit.edu/spd/larch/LSL/index.html)
    - [Larch/C++](https://www.eecs.ucf.edu/~leavens/larchc++.html) (?): Interface Specification Language for C++ (Iowa State Univ.)
    - [Larch/Smalltalk](https://www.eecs.ucf.edu/~leavens/larchSmalltalk.html) (?): Behavioral interface specification language for Smalltalk-80 (Iowa State Univ.)
- [SAL](https://sal.csl.sri.com/) (GPL-2, Scheme): Language for specifying concurrent systems in a compositional way. BDD-based and SAT-based MC, experimental "Witness" MC, "infinite" bounded MC based on SMT solving, simulator, deadlock checker, automated test generator (SRI, Stanford, Berkeley)
    - [Z2SAL](https://staffwww.dcs.shef.ac.uk/people/A.Simons/z2sal/checking.html) (?, Java): transator that generates a SAL automaton from a single Z specification (Univ. of Sheffield)
- [Gappa](http://gappa.gforge.inria.fr/) (GPL-3, CeCILL): for numerical programs dealing with floating-point or fixed-point arithmetic (INRIA)
- [Mizar](http://mizar.org/)
- [NuPRL](http://www.nuprl.org/): Formal Digital Library (Cornell)
- [MuPRL](https://github.com/TOTBWF/muprl) (BSD-3, Haskell): small, mainly instructional, proof assistant in the style of NuPRL
- [MetaPRL](https://www.cs.cornell.edu/jyh/metaprl/default.html)
- [Matita](http://matita.cs.unibo.it/index.shtml) (GPLv3, [OCaml](http://matita.cs.unibo.it/gitweb/?p=helm.git;a=summary)): Interactive theorem prover based on calculus of inductive constructions (Univ. of Bologna)
- [Gandalf](http://deepthought.ttu.ee/it/gandalf/)
- [E-SETHEO](https://www4.informatik.tu-muenchen.de/~schulz/WORK/e-setheo.html): strategy-parallel compositional theorem prover for first-order logic with equality
- [SPASS](https://www.spass-prover.org/): First-Order Logic with Equality (Max Planck Inst. Inf.)
- [Omega](https://github.com/theoremprover-museum/OMEGA) (?, Isabelle/Lisp): for higher-order logic based on proof planning
- [Omega](https://code.google.com/p/omega/) (BSD-3): cross between a purely functional programming language and a theorem prover
- [Zipperposition](https://sneeuwballen.github.io/zipperposition/) (BSD-2, [OCaml](https://github.com/sneeuwballen/zipperposition/)): automatic theorem prover for typed higher-order logic with equality, datatypes and arithmetic, based on superposition and rewriting
- [wikipedia list](https://en.wikipedia.org/wiki/Automated_theorem_proving)
- [this thread](https://cs.stackexchange.com/questions/868/types-of-automated-theorem-provers)
- [jImp](http://symbolaris.com/logic/jImp.html) (binary, Java): based on set of support and ordered resolution for first-order logic, supports: clause indexing techniques, subsumption, and tautology elimination, Davis-Putnam-Loveland-Logemann (DPLL) inference procedure (CMU)
- [QEPCAD](http://www.usna.edu/CS/~qepcad/B/QEPCAD.html) and [github](https://github.com/PetterS/qepcad) (BSD-like, C): Quantifier elimination by partial cylindrical algebraic decomposition (US Naval Academy, Drexel Univ., North Carolina State Univ.)
    - [Mac OS X 10.6, 10.7 binaries](https://www.cl.cam.ac.uk/~lp15/papers/Arith/qepcad-for-mac.html) (Cambridge Univ.)
- [E](http://www4.informatik.tu-muenchen.de/~schulz/E/E.html) (GPL-2, C): Full first-order logic with equality ([TU Munchen](http://www4.in.tum.de/~schulz/Stephan_Schulz/Stephan_Schulz.html))
- [Community Z Tools](http://czt.sourceforge.net/) (GPL-2, Java): Tools for editing, typechecking and animating Z specifications and related notations, including Java framework for building formal methods tools (Univ. Oxford, contrib)
- [ProofPower](https://www.lemma-one.com/ProofPower/index/) (GPL, ?): Tool suite supporting specification and proof in HOL and Z notation (Lemma 1 Ltd)
- [ClawZ](https://www.lemma-one.com/clawz_docs/clawz_docs.html) (?, ?): Simulink -> Z notation (Lemma 1 Ltd)
- [Waldmeister](https://www.waldmeister.org/index.htm) (FUSC, ?): TP for unit equational logic (Max Planck Inst. Informatik)
- [Spear](https://www.domagoj-babic.com/index.php/ResearchProjects/Spear) (?, ?): fast bit-vector arithmetic theorem prover (Google)
- [Metamath](http://us.metamath.org): Tiny language based on ZFC, and also database of proved theorems
- [Theorema](https://github.com/windsteiger/Theorema) (GPLv3, Mathematica): a system for automated reasoning (theorem proving) and automated theory exploration based on Mathematica ([JKU](https://www.risc.jku.at/research/theorema/software/))
- [Princess](http://www.philipp.ruemmer.org/princess.shtml) (GPL-3, Scala): FOL modulo linear integer arithmetic
    - [Seneschal](http://www.philipp.ruemmer.org/seneschal.shtml) (GPL-3, Java): synthesising linear ranking functions for programs expressible in Presburger arithmetic
- [FOL prover](https://github.com/boyers/theorem_prover) (BSD, Python): automated theorem prover for first-order logic, guaranteed to prove any provable formula ([MIT](https://www.stephanboyer.com/))
- [hemera](https://github.com/arademaker/hemera) (?, Python): yet another simple theorem prover (PUC-Rio)
- [FLiP](https://github.com/jon-jacky/FLiP) (GPL, Python): Library for defining logics and writing theorem prover applications, e.g., a proof checker for natural deduction proofs ([Univ. Wasignton](https://staff.washington.edu/jon/))
- [ATS](http://www.ats-lang.org/) (GPL-3, C): A statically typed multiparadigm programming language that unifies implementation with formal specification, using theorem proving (Boston Univ.)
- [F\*](https://www.fstar-lang.org/) (Apache 2.0, [OCaml, F\#](https://github.com/FStarLang/FStar)): ML-like functional programming language aimed at program verification. Its type system includes polymorphism, dependent types, monadic effects, refinement types, and a weakest precondition calculus (MSR, INRIA)
- [`proofcheck`](http://www.proofcheck.org/) (GPL, Python): Checks mathematical proofs written in La/TeX, attempts to handle mathematical language formalized according to the author's preferences as much as possible ([PyPI](https://pypi.python.org/pypi/proofcheck/1.0)) ([Widener Univ.](http://cs.widener.edu/~neveln/))
- [ProofPeer](http://www.proofpeer.net/) (MIT, [Scala/Isabelle](https://github.com/proofpeer)): Collaborative theorem proving ([Edinburgh Univ.](http://www.proofpeer.net/contact.html))
- [Nitpick](https://www.cs.cmu.edu/afs/cs.cmu.edu/project/nitpick/www/home.html) (?): Checker for Z specifications (CMU)
- [Abella](https://abella-prover.org) (GPLv3, [OCaml](https://github.com/abella-prover/abella)): Interactive theorem prover based on lambda-tree syntax, well-suited for reasoning about the meta-theory of programming languages and other logical systems that manipulate objects with binding ([Univ. of Minnesota](https://www-users.cs.umn.edu/~gopalan/), [LIX/École polytechnique](https://www.lix.polytechnique.fr/), [INRIA/Saclay](https://www.inria.fr/en/centre/saclay))
- [GAPT](https://github.com/gapt) (GPLv3, Scala): Framework for transforming and processing proofs, and interfaces to automated reasoning tools (provers, SMT solvers, SAT solvers)
- [homotopy.io](https://homotopy.io) (CC BY-NC 3.0, [JavaScript](https://github.com/homotopy-io/homotopy-webclient)): A proof assistant for n-categories
- [Andromeda](https://www.andromeda-prover.org/) (BSD-2, [OCaml](https://github.com/Andromedans/andromeda)): A proof assistant for general type theories, LCF-style, with statically typed meta-language Andromeda ML
- [Cyclist](https://www.cyclist-prover.org) (BSD-3, [OCaml/C++](https://github.com/ngorogiannis/cyclist): framework for building cyclic theorem provers based on a sequent calculus (Facebook, Middlesex Univ.)
- [LaTTe](https://latte-central.github.io/LaTTe/) (MIT, [Clojure](https://github.com/latte-central/LaTTe)): proof assistant designed as a library for the Clojure programming language and environment, based on a simple dependent-typed lambda-calculus (a variant of λD)
- [Alg](https://github.com/andrejbauer/alg) (BSD-2, OCaml): A program that generates all finite models of a first-order theory. It is optimized for equational theories.
- [RZ](https://github.com/andrejbauer/rz) (MIT, OCaml): A tool for automatic generation of specifications based on realizability theory
- [LEGO](http://www.dcs.ed.ac.uk/home/lego/) (?, [ML](https://github.com/theoremprover-museum/LEGO)): an interactive proof development system (proof assistant), implementing various related type systems: the Edinburgh Logical Framework (LF), the Calculus of Constructions (CC), the Generalized Calculus of Constructions (GCC) and the Unified Theory of Dependent Types (UTT) (Univ. of Edinburgh)
- [IMPS](https://github.com/theoremprover-museum/imps) (MITRE, Perl/Lisp): Intended to provide mechanical support for traditional mathematical techniques and styles of practice, with underlying logic simple type theory (MITRE)
- [Museum of theorem provers](https://theoremprover-museum.github.io): front-end to a collection of source code repositories for theorem provers, hosted on GitHub
- [Scriptie](https://github.com/deosjr/Scriptie) (?, Python): theorem prover for Lambek-Grishin calculus
- [set-theory-prover](https://github.com/timjb/set-theory-prover) (BSD-3, Haskell): simple LCF-style proof assistant for ZFC
- [Jape](https://github.com/RBornat/jape) (GPLv2, OCaml/Java): a configurable proof editor, best at natural deduction and sequent calculus
- [Geo](https://ii.uni.wroc.pl/~nivelle/software/geo/index.html) (GPLv3, C++): prover for full-first order logic, based on geometric resolution calculus (Univ. of Wrocław)
- [UTP2](https://www.scss.tcd.ie/Andrew.Butterfield/Saoithin/) (GPLv2, Haskell): a theorem proving assistant for 2nd-order predicate calculus, designed to support foundational proof work in the Unifying Theories of Programming (UTP) framework
- [UTP-Calculator](https://bitbucket.org/andrewbutterfield/utp-calculator/src/master/) (MIT, Haskell): a tool that supports rapid prototyping of new theories in the Unifying Theories of Programming paradigm, by supporting an easy way to very quickly perform test calculations
- [holpy](https://gitee.com/bhzhan/holpy) (BSD-3, Python): implementation of higher-order logic in Python (Institute of Software, Chinese Academy of Sciences)
- [llprover](https://cspsat.gitlab.io/llprover/) (?, Prolog): Linear logic prover that searches for cut-free proofs of two-sided sequents of first-order linear logic
- [seqprover](https://cspsat.gitlab.io/seqprover/) (?, Prolog): Sequent prover that searches for a cut-free proof of the given sequent of first-order logic

## Theorem provers for modal logics

- [ls4](https://github.com/quickbeam123/ls4) (MIT, C++, C): PLTL prover based on labelled superposition with partial model guidance, with MiniSAT behind, and used as backend by TLAPS ([Univ. Manchester](https://forsyte.at/people/suda/))
- [T2](https://mmjb.github.io/T2/) (F\#, Mono, MIT): Prover of CTL\* of programs, with `z3` behind (replaces TERMINATOR) ([MSR](http://research.microsoft.com/en-us/people/mabrocks/), [UCL](https://heidyk.com/))
- [TRP++](https://cgi.csc.liv.ac.uk/~konev/software/trp++/) [files](https://cgi.csc.liv.ac.uk/~konev/software/trp++/translator/) (GPL-2, C++): theorem prover for PLTL based on the temporal resolution calculus ([Univ. Liverpool](https://cgi.csc.liv.ac.uk/~konev/))
    - [TRP](https://cgi.csc.liv.ac.uk/~ullrich/TRP/) (?, Prolog): earlier implementation of TRP++
- [LWB](https://github.com/esb-lwb/lwb) (EPL, Clojure): The Logics Workbench, prover for propositional, predicate and linear temporal logic
    - [`lwb-gui`](https://github.com/esb-lwb/lwb-gui) (EPL, Clojure): simple GUI for the Logic Workbench lwb
- [TRS](http://www.sc.ehu.es/jiwnagom/paginaMarisa_archivos/TRS.html) (?, ?): Resolution-based theorem prover for PLTL, [online interface](https://trs-tool.appspot.com/) only (UBC)
- [TLPVS](https://www.cs.nyu.edu/acsys/tlpvs/tlpvs.html): PVS implementation of an LTL verification system (NYU)
- [STeP](https://www-step.stanford.edu/): Stanford temporal prover
- [CTLSAT](https://github.com/nicolaprezza/CTLSAT) (?, C++): CTL satisfiability solver
- [MLSolver](https://github.com/tcsprojects/mlsolver) (?, Ocaml): Solver for satisfiability and validity of modal fixpoint logics (Univ. Munich, Univ. Kassel)
- [Leviathan](https://github.com/Corralx/leviathan) (BSD-3, C++): Tableau prover for LTL satisfiability (Univ. Udine)
- [PLTLProvers](https://users.cecs.anu.edu.au/~rpg/PLTLProvers/): (?, OCaml): 3 PLTL theorem prover variants
- [LoTREC](https://www.irit.fr/Lotrec/) (FSLA): Generic tableau prover
- [MleanTAP](http://www.leancop.de/mleantap/) (?, Prolog): Sound and complete theorem prover based on free-variable semantic tableaux extended by an additional prefix unification (logics: D, T, S4, S5) (TU Darmstadt)
- [List of tools for modal logics](http://www.cs.man.ac.uk/~schmidt/tools/) (Univ. Manchester)
- [Schuppan-Darmawan](https://www.schuppan.de/viktor/atva11/) benchmark results of LTL satisfiability solvers
- [TPTP](http://www.tptp.org): Problem library for automated theorem proving (Univ. Miami)
- [QMLTP](http://www.iltp.de/qmltp/systems.html): Benchmarking results for theorem provers for first-order modal logics
- [Modal Logic Playground](https://rkirsling.github.io/modallogic/) (MIT, [JavaScript, HTML](https://github.com/rkirsling/modallogic)): a graphical semantic calculator for modal propositional logic

## QBF
- [QBF Solvers](https://www.cs.toronto.edu/~fbacchus/qbf.html#PreQuel) (C++)
- [RAReQS](http://sat.inesc-id.pt/~mikolas/sw/areqs/) (GPL, C++/uses MiniSAT): Recursive abstraction refinement QBF solver ([INESC-ID Lisboa](http://sat.inesc-id.pt/~mikolas/))
- [Quantor](http://fmv.jku.at/quantor/) (BSD-4, C): QDIMACS input (ETHZ, JKU)
- [DepQBF](https://lonsing.github.io/depqbf/) (GPL, C): search-based ([TU Wien](http://www.kr.tuwien.ac.at/staff/lonsing/), JKU)
- [nenofex](https://github.com/lonsing/nenofex) (GPL, C): expansion-based for NNF ([TU Wien](http://www.kr.tuwien.ac.at/staff/lonsing/), JKU)
- [CAQE](https://www.react.uni-saarland.de/tools/caqe/) (Apache-2, C): certifying solver based on CEGAR-based clausal abstraction (Saarland Univ., UC Berkeley)
- [QBFLIB](http://vlsicad.eecs.umich.edu/BK/Slots/cache/www.qbflib.org/): Collection of benchmark problems, solvers, and tools related to Quantified Boolean Formula (QBF) satisfiability (Univ. Michigan)

## SAT
- [SAT Live](https://www.satlive.org/): news outlet

### CDCL

- [MiniSat](http://minisat.se/) and its [github](https://github.com/niklasso/minisat) (MIT, C++/C): minimalistic high-performance solver to help get started ([Chalmers Univ.](http://minisat.se/Authors.html))
    - [`simplesat`](https://github.com/enthought/sat-solver) (BSD-3, Python): Python implementation based on MiniSat, for handling package dependencies
    - [ruby-minisat](https://github.com/mame/ruby-minisat) (MIT, Ruby): bindings
    - [qmaxsat](https://sites.google.com/site/qmaxsat/) (MIT, C/C++): Q-dai MaxSAT Solver, based on MiniSat
    - [MiniMarch](http://www.st.ewi.tudelft.nl/sat/minimarch.php)
    - [Glucose](https://www.labri.fr/perso/lsimon/glucose/): CDCL with new scoring scheme for clause learning (CRIL)
    - [MiniSAT+](https://github.com/niklasso/minisatp)
- [Lingeling, Plingeling, Treengeling](http://fmv.jku.at/lingeling/)
- [PicoSAT](http://fmv.jku.at/picosat/) (MIT, C)
    - [Python bindings](https://pypi.python.org/pypi/pycosat) (MIT, Python)
    - [`pigosat`](https://github.com/wkschwartz/pigosat) (BSD, Go): bindings
- [`cadical`](https://github.com/arminbiere/cadical) (MIT, C++): satisfiability solver that is intended to be understood and changed
- [Sat4j](https://www.sat4j.org/) (EPL or LGPL, Java): SAT, MAXSAT, Pseudo-Boolean, MUS (Artois Univ., CNRS, CRIL)

### Stochastic local search
- [UBCSAT](http://www.satlib.org/ubcsat/): (Univ. British Columbia)
- [`clsat`](https://github.com/vegard/clsat) (GPLv2, C++): small, incomplete, stochastic local search, OpenCL-based SAT
solver

### Parallel
- [PeneLoPe](https://www.cril.univ-artois.fr/~hoessen/penelope.html) (BSD-like C++) (CRIL)
- [CombiSAT](https://github.com/stefanbucur/CombiSAT) (?, Python): Portfolio solver running multiple sequential solvers with different strategies ([EPFL](https://people.epfl.ch/stefan.bucur))
- [PWBO](http://sat.inesc-id.pt/pwbo/)

### Unsorted
- [zChaff](https://www.princeton.edu/~chaff/zchaff.html) (Princeton Open Source): Chaff algorithm ([Princeton](https://www.princeton.edu/~chaff/))
- [SATABS](https://www.cprover.org/satabs/) (BSD, C): ANSI-C, C++ verification via Boolean program abstraction (Univ. Oxford, Imperial College, Univ. Lugano, CMU)
- [NanoSAT](http://fmv.jku.at/nanosat/) (BSD): (JKU)
- [Boppo](https://www.cprover.org/boppo/) (?): MC for Boolean programs featuring: POR, Fixpoint detection using QBF, support for `constraint` construct (Univ. Oxford, Microsoft Research, Univ. Lugano, CMU)
- [CSIsat](https://www.sosy-lab.org/~dbeyer/CSIsat/) (Apache): Interpolating decision procedure for the quantifier-free theory of rational linear arithmetic and equality with uninterpreted function symbols (EPFL, SFU)
- [MSUnCore](http://logos.ucd.ie/wiki/doku.php?id=msuncore): solving (Weighted) (Partial) Maximum Satisfiability (MaxSAT)
- [antom](https://projects.informatik.uni-freiburg.de/projects/antom) (C++): Lib solving: SAT, Unweighted MaxSAT, Partial MaxSAT, \#SAT (Uni. Freiburg)
- [SCIP](https://scip.zib.de/): Mixed int programming (MIP), constraint int programming and branch-cut-and-price
    - [scip-maxsat](https://github.com/msakai/scip-maxsat) (ZIB, C++): Max-SAT frontend for SCIP
- [GLPK](https://www.gnu.org/software/glpk/)
    - [MaxSAT frontend](https://github.com/msakai/glpk-maxsat) for GLPK
- [PrecoSAT](http://fmv.jku.at/precosat/) (MIT-like)
- [RSat](http://reasoning.cs.ucla.edu/rsat/home.html)
- [fss](https://dudka.cz/fss) (GPL-3, C++/GAlib): Genetic algorithms
- [MiFuMaX](http://sat.inesc-id.pt/~mikolas/sw/mifumax/) (GPL-3)
- [Shaowei Cai solvers](http://shaoweicai.net/research.html)
- [algorithms](https://github.com/msakai/toysolverw)
- [WBO](http://sat.inesc-id.pt/wbo/): Weighted Boolean Optimization Solver that extends Weighted-Partial MaxSAT and Pseudo-Boolean Optimization
    - [open-WBO](http://sat.inesc-id.pt/open-wbo/) (MIT, C++): open source version of WBO
- [ToulBar2](https://mulcyber.toulouse.inra.fr/projects/toulbar2/) (GPL, C++): weighted constraint satisfaction solver (INRA)
- [march](http://www.isa.ewi.tudelft.nl/sat/march.htm): DPLL with lookahead heuristics (TU Delft)
- [march_eq](http://www.st.ewi.tudelft.nl/sat/march_eq.htm): (TU Delft)
- [march_dl](http://www.st.ewi.tudelft.nl/sat/march_dl.php): (TU Delft)
- [CryptoMiniSat](https://www.msoos.org/cryptominisat2/), its [github](https://github.com/msoos/cryptominisat) (LGPL, C++, Python)
- [WinSAT](https://www.mqasem.net/sat/winsat/)
- [HyperSAT](https://www.domagoj-babic.com/index.php/ResearchProjects/HyperSAT) (FUSC, C): research SAT solver written to experiment with B-cubing search space pruning
- [iSAT](https://projects.avacs.org/projects/isat/): DPLL-style solver developed for large Boolean combinations of non-linear arithmetic constraints involving transcendental functions
- [HySAT](https://www.uni-oldenburg.de/hysat/)
- [Scarab](http://kix.istc.kobe-u.ac.jp/~soh/scarab/) (BSD, Scala): SAT-based constraint programming
- [Limboole](http://fmv.jku.at/limboole/) (Unlicense, ?): satisfiability of arbitrary structural formulas, not just CNF
- [MiFuMaX](http://sat.inesc-id.pt/~mikolas/sw/mifumax/)
- [UBCSAT](https://github.com/dtompkins/ubcsat) (FUSC, C): Stochastic local search solver (Univ. British Columbia)
- [QNF2z3](http://sat.inesc-id.pt/~mikolas/sw/qcnf2smt/) (FUSC, Python/Bash): invoking Z3 on QDIMACS instances (INESC Lisboa)
- [ToughSAT](https://toughsat.appspot.com/): generates "difficult" SAT instances
- [minibones](http://sat.inesc-id.pt/~mikolas/sw/minibones/) (FUSC): computing backbone literals
- [SBSAT](https://www.cs.uc.edu/~weaversa/SBSAT.html): state-based  (U Cincinnati)
- [satsolver](https://github.com/stephenroller/satsolver) (?, Python): DPLL implementation for educational purposes
- [Potassco](http://potassco.sourceforge.net/): answer set programming collection: Clasp, Gringo, Clingo, Aspcud, Clingcon, claspfolio, coala solvers
- [miniC2D](http://reasoning.cs.ucla.edu/minic2d/) (?): knowledge compilation and model counting based on exhaustive DPLL (UCLA)
- [toulbar2](https://miat.inrae.fr/toulbar2/) (GPL, [C++](https://github.com/toulbar2/toulbar2)): Exact solver for cost function networks (INRIA, Barcelona)


## SMT
- CVC5:
  - [CVC5](https://cvc5.github.io) (BSD-3, [C++](https://github.com/cvc5/cvc5)): successor of CVC4 (Stanford, NYU, Univ. Iowa, EPFL, Joseph Fourier Univ., Oxford Univ., SRI)
  - [CVC4](https://cvc4.github.io) (BSD-3, [C++](https://github.com/CVC4/CVC4-archived)): built-in base theories, quantifiers, interactive text-based interface, interfaces to: C/C++, Python, Java, OCaml, PHP, Perl, Ruby, Tcl, model generation, [predecessor](https://cvc4.github.io/2021/04/02/cvc5-announcement.html) of CVC5 (Stanford, NYU, Univ. Iowa)
  - [LFSC](https://github.com/CVC4/LFSC) (BSD-style, C++): proof checker for LFSC proofs generated by CVC4 (Univ. of Iowa)
  - [rlfsc](https://lib.rs/crates/rlfsc) (MIT/Apache and LGPLv3, Rust): a checker for the LFSC proof language
  - [CVC3](https://www.cs.nyu.edu/acsys/cvc3/) (BSD-3, [C++](https://github.com/msakai/cvc3)): [predecessor](https://cvc4.github.io/history.html) of CVC4 (Stanford, NYU, Univ. Iowa)
  - [CVC Lite](https://cs.nyu.edu/acsys/cvcl/doc/index.html) (?, C++): [predecessor](https://cvc4.github.io/history.html) of CVC3, successor of CVC (Stanford, NYU)
  - [CVC](https://doi.org/10.1007/3-540-45657-0_40) (open, C/C++): Cooperating Validity Checker, [predecessor](https://cvc4.github.io/history.html) of CVC Lite (Stanford)
  - [SVC](https://doi.org/10.1007/BFb0031808) (GPLv2, C/C++): [predecessor](https://cvc4.github.io/history.html) of CVC (Stanford)
  - [CVCHOL](https://cs.nyu.edu/acsys/cvc3/cvchol) (BSD-3, OCaml): proof translator that translates CVC3 theorems into HOL Light theorems (NYU)
- [Z3](https://github.com/Z3Prover/z3) (MIT, C++/Python): `.smt2`, `.dimacs`, `.cnf`, `.dl`, `.smt` (Microsoft Research)
    - [Z3_Haskell](https://github.com/kayceesrk/Z3_Haskell) (BSD, Haskell): bindings for Z3 (Cambridge Univ.)
    - [`hz3`](https://github.com/tizmd/hz3) (BSD, Haskell): bindings to low-level API for Z3
    - [ScalaZ3](https://lara.epfl.ch/w/scalaz3) (Apache-2.0, [Scala](https://github.com/epfl-lara/ScalaZ3/)): bindings for Z3 (EPFL)
    - [bapa-z3](https://github.com/psuter/bapa-z3) (BSD, Scala): Boolean algebra with Presburger arithmetic constraints plug-in for Z3 (EPFL)
    - [Z3-str](https://github.com/z3str/Z3-str) (MIT, C++/Python): string theory plug-in for Z3 (Purdue)
    - [Z3Fs](https://github.com/dungpa/Z3Fs) (MIT, F\#): DSL for SMT problems using Z3 API in F\#
    - [z3-turnkey](https://github.com/tudo-aqua/z3-turnkey) (ISC, Kotlin/Java): Build system for Z3 that creates a self-unpacking, standalone JAR file that ships all required native support code and automatically unpacks it at runtime
    - [z3-floating-point-proofs](https://github.com/xennygrimmato/z3-floating-point-proofs) (MIT, Python): automated proofs about floating-point numbers using the Z3 theorem prover
- [iZ3](https://rise4fun.com/iZ3) ([FUSC](https://z3.codeplex.com/license), C++/Python): Interpolating, supports: arithmetic, arrays, uninterpreted functions, and quantifiers (Microsoft Research)
- [Yices](https://yices.csl.sri.com) (GPLv3, [C](https://github.com/SRI-CSL/yices2)): SMT solver that decides the satisfiability of formulas containing uninterpreted function symbols with equality, real and integer arithmetic, bitvectors, scalar types, and tuples. Supports both linear and nonlinear arithmetic. Reads input from SMT-LIB or Yices' own specification language, includes Python bindings (SRI/CSL)
    - [`yices`](https://github.com/SRI-CSL/yices2_python_bindings) (MIT, Python): Python bindings for yices2 (SRI CSL)
- [Boolector](http://fmv.jku.at/boolector/) (GPL-3): bit-vectors and arrays (Johannes Kepler Univ. Linz, Upper Austrian Univ. of Applied Sciences)
- [MathSAT](https://mathsat.fbk.eu/download.html) (FUSC, C++, Python/Java bindings): Theories: equality and uninterpreted functions, linear arithmetic, bit-vectors, and arrays, and Functionalities: computation of Craig interpolants, extraction of unsatisfiable cores, generation of models and proofs, and the ability of working incrementally (FBK, Univ. Trento)
- [SMT-LIB](https://www.cprover.org/SMT-LIB-LSM/) (?, C++): format for Finite lists, sets, maps (Oxford Univ.)
- [Alt-ERGO](https://alt-ergo.ocamlpro.com) (FUSC, [OCaml](https://github.com/OCamlPro/alt-ergo)): built upon CC(X) algorithm (INRIA, Univ. Paris Sud, CNRS, LRI)
- [mSAT](https://gbury.github.io/mSAT/) (Apache-2.0, [OCaml](https://github.com/Gbury/mSAT)): Modular SAT/SMT solver with proof output, derives from ERGO (INRIA)
- [veriT](https://www.verit-solver.org/) (BSD-2, C/C++): proof-producing SMT solver, complete for quantifier-free formulas with uninterpreted functions and difference logic on real numbers and integers ([2017 version](https://doi.org/10.5281/zenodo.582482)) (INRIA, Nancy Univ., UFRN, CNPq, Loria)
    - [haRVey](http://harvey.loria.fr/) (LGPL/BSD-2, C/C++): Predecessor of veriT: haRVey-FOL (LGPL), haRVey-SAT (BSD-2) (INRIA, Nancy Univ., UFRN, CNPq, Loria)
- [dReal](http://dreal.github.io) (Apache-2.0, [C++](https://github.com/dreal/dreal4)): SMT solver for nonlinear theories of reals, produces proofs for unsat cases, includes a semi-algorithm for proof-checking, has Python bindings ([PyPI](https://pypi.org/project/dreal/))
- [SMT-RAT](https://smtrat.github.io) (MIT, [C++](https://github.com/ths-rwth/smtrat)): Toolbox for strategic and parallel satisfiability-modulo-theories solving (RWTH)
- [Vampire](https://vprover.github.io): proof-producing theorem prover that can read SMT-LIB input, see section on Theorem Provers
- [archsat](https://github.com/Gbury/archsat) (MIT, OCaml): proof-producing SMT/McSAT solver, handling polymorphic first-order logic, using an SMT/McSat core extended using tableaux, superposition, and rewriting
- [BEAGLE](https://bitbucket.org/peba123/beagle/src/master/) (BSD, Scala): theorem prover for first-order logic with equality over linear integer/rational/real arithmetic that takes input in SMT-LIB 2.0, FOF, TFF, TFF-INT formats (NICTA)
- [Fx7](https://moskal.me/smt/en.html) (?, Nemerle): prover based on C\# port of MiniSAT
- [Simplify](https://kindsoftware.com/products/opensource/Simplify/), its [github](https://github.com/kiniry/Simplify) (?, Modula-III): (SRC)
- [Beaver](https://uclid.eecs.berkeley.edu/jha/beaver-dist/beaver.html) (BSD, OCaml): for the theory of quantifier-free finite-precision bit-vector arithmetic (UC Berkeley)
- [SBV](https://github.com/LeventErkok/sbv) (BSD-3, Haskell): SMT based verification in Haskell: Express properties about Haskell programs and automatically prove them using SMT solvers (ABC, Boolector, CVC4, MathSAT, Yices, Z3). ([Intel](https://leventerkok.github.io/))
- [list of SMT solvers](https://smtlib.cs.uiowa.edu/solvers.shtml) (Univ. Iowa)
- [Decision Procedures: An Algorithmic Point of View](https://www.decision-procedures.org/software/) (BSD-4, C++): software that accompanies the book [Decision Procedures](https://www.decision-procedures.org)
- [`llvm2smt`](https://github.com/SRI-CSL/llvm2smt) (MIT, OCaml): Experimental translation of LLVM (3.5ish) IR to SMT-LIB (SRI CSL)
- [JavaSMT](https://github.com/sosy-lab/java-smt) (Apache-2.0, Java/C): unified Java API for SMT solvers
- [`bv2epr`](http://fmv.jku.at/bv2epr/) (GPLv3, C): tool for translating a QF\_BV formula in SMT2 format into an EPR clause set in TPTP format (JKU)
- [PySMT](https://github.com/pysmt/pysmt) (Apache-2.0, Python): a library for SMT formulae manipulation and solving, with interfaces to z3, MathSAT, CVC4, Yices, CUDD, PicoSAT, Boolector, and any solver that reads SMT-LIB (includes SMT-LIB parser written in Python)
- [ddSMT](https://github.com/aniemetz/ddSMT) (GPLv3, Python): a delta debugger for SMT benchmarks in SMT-LIB v2, it serves as an input minimizer for SMT benchmarks on which a given executable shows unexpected or faulty behavior and supports all SMT-LIB v2 logics (includes SMT-LIB parser written in Python)
- [`smtpp`](https://github.com/rbonichon/smtpp) (MIT, OCaml): a preprocessor for SMT-LIB 2.0 scripts with extensions for lambda-terms and polymorphic types in scripts (Inria, Universite de Nancy 2, Universidade Federal
do Rio Grande do Norte)
- [SMTtoTPTP](https://bitbucket.org/peba123/smttotptp/src/master/) (GPLv3, Scala): a translator for problems written in the SMT-LIB language, version 2, to the TPTP TFF language, supporting quantified formulas over the combined theories of of free symbols, arrays, integer and real arithmetic. It also supports Z3-style datatype declarations and some other extensions.

## Constraint Solving Problem (CSP) solvers
- [`constraint`](https://github.com/python-constraint/python-constraint) (BSD-2, Python): Constraint Solving Problem resolver for Python (on [PyPI](https://pypi.org/project/python-constraint/)) (Canonical)
- [Cassowary](https://overconstrained.io/): incremental constraint solving toolkit that efficiently solves systems of linear equalities and inequalities. Constraints may be either requirements or preferences. Client code specifies the constraints to be maintained, and the solver updates the constrained variables to have values that satisfy the constraints, site source on [GitHub](https://github.com/Overconstrained/Overconstrained)
    - [Cassowary](https://constraints.cs.washington.edu/cassowary/) (LGPLv2, C++): (original implementation)  incremental constraint solving toolkit that efficiently solves systems of linear equalities and inequalities. Constraints may be either requirements or preferences. Re-solving the system happens rapidly, supporting UI applications. ([Univ. of Washington](https://www.cs.washington.edu/people/faculty/borning/))
    - [RHEA](https://github.com/Nocte-/rhea) (MIT, C++): modernized C++ version of the original Cassowary implementation
    - [Kiwi](https://kiwisolver.readthedocs.io/en/latest/) (BSD-3, [C++/Python](https://github.com/nucleic/kiwi)): new implementation of the algorithm based on the Cassowary paper, 10x to 500x faster than the original, with Python bindings (Nucleic Development Team)
    - [`cassowary`](https://github.com/brodderickrodriguez/cassowary) (BSD-3 and Apache-2.0, Python): pure python implementation of the Cassowary constraint solving algorithm, available [on PyPI](https://pypi.org/project/cassowary) (Auburn Univ.)
    - [Casuarius](https://github.com/enthought/casuarius) (LGPLv2.1, C++/Python): Cython bindings for the Cassowary Constraint Solving Toolkit version 0.6
    - [Aqt.Cassowary](https://ableton.github.io/aqt-cassowary/) (MIT, [QML/C++/JavaScript](https://github.com/Ableton/aqt-cassowary)): Qt plugin that allows running an incremental linear constraint solver in QML applications, and wraps RHEA
- Babelsberg:
    - [Babelsberg/JS](https://babelsberg.github.io/babelsberg-js/) (BSD-3, [JavaScript](https://github.com/babelsberg/babelsberg-js)): object constraint programming language and implementation, using the solvers Z3, DeltaBlue, and Cassowary
    - [`pybelsberg`](https://github.com/Pybelsberg/pybelsberg) (BSD-3, Python): implementation of Babelsberg allowing constraint-based programming in Python, using the Z3 theorem prover

## Other solvers
- [RSolver](http://rsolver.sourceforge.net/) (LGPL, OCaml/C/Java): Quantified inequality constraints ([Academy of Sciences Czech Republic](https://www.cs.cas.cz/~ratschan/))
- [ROSETTE](https://people.csail.mit.edu/emina/pubs/rosette.onward13.pdf): Framework for designing solver-aided languages, realized embedded in [Racket](https://racket-lang.org/) ([UC Berkeley, MIT](https://people.csail.mit.edu/emina/))

## Logic programming
- [miniKanren](http://minikanren.org/)
- [logpy](https://github.com/logpy/logpy)

# Software Synthesis
- [Leon](https://lara.epfl.ch/w/leon), its [github](https://github.com/epfl-lara/leon) (BSD-2, Scala): Automated system for synthesizing and verifying functional Scala programs (EPFL)
    - [COMFUSY](https://lara.epfl.ch/w/comfusy) (BSD-2, [Scala](https://github.com/epfl-lara/comfusy)): tool for synthesizing executable code from specifications in linear integer arithmetic and constraints on sets of objects (EPFL)
    - [Kaplan](https://lara.epfl.ch/w/kaplan) (?, Scala): Scala extension that supports constraint-solving (EPFL)
    - [RegSy](https://lara.epfl.ch/w/regsy) (?, Scala): synthesis tool that can be used to build functions from specification written in WS1S (EPFL)
- [AutoBayes](https://ti.arc.nasa.gov/opensource/projects/autobayes/) (NOSA, Prolog): automatic generation of customized algorithms from compact, declarative specifications in the data analysis domain, requires SWI Prolog, generates OCtave/Matlab code (NASA)
- [Jeeves](https://projects.csail.mit.edu/jeeves/) (MIT, [Python](https://github.com/jeanqasaur/jeeves)): programming language for automatically enforcing privacy policies and Python implementation (MIT)
- [MCGP](https://sites.google.com/site/galkatzzz/mcgp-tool) (?, ?): automatic generation and correction of programs, based on model cheking and genetic programming (Bar-Ilan Univ.)

# Runtime Verification
- [MOP](https://fsl.cs.illinois.edu/index.php/MOP) (Java): Monitoring-Oriented Programming ([UIUC](https://fsl.cs.illinois.edu/index.php/Main_Page))
    - [JavaMOP](https://fsl.cs.illinois.edu/index.php/JavaMOP4) (MIT, [Java](https://github.com/runtimeverification/javamop)): Runtime verification system for Java, using AspectJ for instrumentation (UIUC)
    - [ROSMOP](https://fsl.cs.illinois.edu/index.php/ROSMOP) (?, [Java](https://github.com/Formal-Systems-Laboratory/rosmop)): Monitor Oriented Programming for ROS (UIUC)
- [CHIMP](https://www.cs.rice.edu/CS/Verification/Software/software.html): LTL -> monitors: nondeterministic finite-word automata that accept all illegal executions (Rice Univ.)
- [LTL_3](http://ltl3tools.sourceforge.net/) (GPL): LTL -> Moore FSM monitor
- [TOPL](https://rgrig.github.io/topl/) (OCaml): monitor Java programs
- [Breach Toolbox](https://github.com/decyphir/breach)(BSD-3, MATLAB/C++): Simulation-based design of dynamical, cyber-physical, and hybrid systems (UC Berkeley, [Decyphir](https://www.decyphir.com/))
- [JTorX](https://fmt.ewi.utwente.nl/redmine/projects/jtorx/wiki/) (BSD-3, Java): Model-based testing: Spec: Aldebaran or GraphML or dot or Jararaca or `.sax` or muCRL or `.bcg` or LOTOS, Implementation either these or real program (Univ. Twente)
- [TorX](https://fmt.cs.utwente.nl/tools/torx/introduction.html) (Apache, ?): Conformance testing of reactive software (Univ. Twente, TU Eindhoven, Philips, Lucent)
- [MonPoly](https://sourceforge.net/projects/monpoly/) (?, OCaml): a prototype monitoring tool that checks compliance of log files with respect to policies specified in MFOTL (Metric First-Order Temporal Logic)
- [Montre](https://github.com/doganulus/montre) (GPL-3, [Pure](https://agraef.github.io/pure-lang/)/C++): A timed regular expression matcher ([Verimag](http://doganulus.com))
- [ROSRV](https://github.com/Formal-Systems-Laboratory/ROSRV) (NCSA, [C++/Java](https://github.com/Formal-Systems-Laboratory/ROSRV)): runtime verification framework for the Robot Operating System (ROS) (Univ. of Illinois at Urbana-Champaign)

# Yet un-categorized
- [Matching Logic](http://www.matching-logic.org/index.php/Matching_Logic): regard a language through both operational and axiomatic lenses at the same time ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
- [Separation logic and local reasoning](https://wiki.mpi-sws.org/star/ToolSupport): wiki and tools list [Max Planck Inst. for Soft. Sys.](https://www.mpi-sws.org/~viktor/)
- [QMRes](https://www.cs.rice.edu/CS/Verification/Software/software.html): Multi-resolution with ZDDs implementation
- [MTSA](https://sourceforge.net/projects/mtsa/) (Public): Modal Transition Systems Analyser (Imperial College London, Univ. Buenos Aires)
- [MoTraS](https://anna.fi.muni.cz/%7Exbenes3/MoTraS/) (?, C++): verification of (disjunctive) modal transition systems, using `ltl2dstar` for LTL to Rabin automaton translation
- [FoCs](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.23.9941)
- [COMPASS](http://compass.informatik.rwth-aachen.de/): correctness, modeling and preformance of aerospace systems
- [VeriSoft](http://cm.bell-labs.com/who/god/verisoft/): systematic software testing (Bell Labs)
- [FTS](https://projects.info.unamur.be/fts/): featured transition systems
- [PdTrav](http://fmgroup.polito.it/index.php/download/viewcategory/3-pdtrav-package)
- [seL4](https://sel4.systems) ([GPLv2, BSD-2](https://github.com/seL4/seL4/blob/master/LICENSE.md), [C](https://github.com/seL4/seL4)): A microkernel formally proved correct, with [proofs in Isabelle/HOL](https://github.com/seL4/l4v)
- [Cogent](https://ts.data61.csiro.au/projects/TS/cogent.pml) (BSD-2, Isabelle/Haskell/C): code and proof co-generation from a purely functional language, on top the seL4 microkernel (CSIRO)
- [Theory of X-Machines](https://x-machines.net): X-machines were introduced in 1974 by [Samuel Eilenberg](https://en.wikipedia.org/wiki/Samuel_Eilenberg)

# TypeSetting
- [LTL](https://github.com/malteschmitz/ltl) (LPPL, LaTeX/TikZ): Configurable LTL math operators with LaTeX and TikZ or LTLFonts
- [fsmtex](https://github.com/benob/fsmtex) (?, Perl/TeX): FSM drawing in LaTeX using TikZ ([Univ. Marseille](https://pageperso.lif.univ-mrs.fr/~benoit.favre))

# Other tool lists
- [Wikipedia](https://en.wikipedia.org/wiki/List_of_model_checking_tools)
- [Yahoda](https://anna.fi.muni.cz/yahoda/) [Masaryk Univ.]
- [wikia](https://formalmethods.wikia.com/wiki/VL) (by Jonathan Bowen)
- [formal methods wiki](https://web.archive.org/web/20070706205223/http://vl.fmnet.info/) (older version of the above)
- [UPenn Hybrid System Tools Repository](http://wiki.grasp.upenn.edu/hst/index.php?n=Main.HomePage)
- [VERIMAG Tools](https://www-verimag.imag.fr/Tools,12.html?lang=)
- [verification tools for industrial automation](http://www.chihhongcheng.info/tools)
- [Carloni et al.](https://www.nowpublishers.com/articles/foundations-and-trends-in-electronic-design-automation/EDA-001)
- [Networked Control Systems Repository](http://filer.case.edu/org/ncs/)
- [rise4fun](https://rise4fun.com/)
- [CMU tools](https://www.cs.cmu.edu/~modelcheck/code.htm)
- [SRI tools](http://fm-wiki.csl.sri.com/index.php/Main_Page) and older [page](https://fm.csl.sri.com/)
- [SYNALP](http://www.inrialpes.fr/synalp/): SYNchronous Applications, Languages, and Programs
- [ARS](http://www-formal.stanford.edu/clt/ARS/): Database of Automated Reasoning Systems ([Stanford](http://blackforest.stanford.edu/clt/))
- [AVACS](http://www.avacs.org/tools/)
- [Quasimodo](http://www.quasimodo.aau.dk/tools.html): Quantitative system properties in model-driven-design of embedded systems
- [Tools list at SMT-LIB](https://smtlib.cs.uiowa.edu/utilities.html)
- [Max-SAT 2013 solvers](http://maxsat.ia.udl.cat:81/13/solvers/index.html)
- [SAT competition](http://www.satcompetition.org/)
- [JKU tools](http://fmv.jku.at/software/index.html)
- [Freek Wiedijk](https://www.cs.ru.nl/~freek/digimath/bycategory.html#tacticprover)
  - [Formalizing 100 Theorems](https://www.cs.ru.nl/~freek/100/): which theorems have been formalized in which prover
- [Proof Assistants, Wikipedia](https://en.wikipedia.org/wiki/Proof_assistant)
- [Univ. Utah tools](http://www.cs.utah.edu/formal_verification/hevea-index.html#htoc2)
- [SV-COMP 2014](https://sv-comp.sosy-lab.org/2014/participants.php): competition on software verification at TACAS 2014
- [Every Proof Assistant Seminar](http://math.andrej.com/2020/04/28/every-theorem-prover/): series of (online) seminars

# databases and benchmarks
- [Model checking benchmarking scripts](https://ti.arc.nasa.gov/m/profile/kyrozier/benchmarking_scripts/benchmarking_scripts.html) (NASA SA, Perl): details on the experiments described in "LTL satisfiability checking" (NASA)
- [VLTS](https://cadp.inria.fr/resources/vlts/): MC benchmarks (CWI/SEN2, INRIA/VASY)
- [BEEM](https://anna.fi.muni.cz/models/): MC benchmarks ([Masaryk Univ.](https://anna.fi.muni.cz/))
- [Mutual Exclusion Promela Source Codes](https://www.ueda.info.waseda.ac.jp/~kobayashi/Promela/benchmark/index.html): (Waseda Univ.)
- [Buchi Store](http://buchi.im.ntu.edu.tw/index.php/home/index/)
- [Promela Database](http://www.albertolluch.com/research/promelamodels): (IMT Lucca)
- [Spec Patterns](http://patterns.projects.cis.ksu.edu/): patterns commonly occuring in specs of concurrent/reactive systems (LTL, CTL, GIL, QRE, ACTL, RAFMC) (Univ. Massachusetts Amherst)
- [Hybrid system safety verification benchmarks](http://hsolver.sourceforge.net/benchmarks/)
- [TPTP](http://www.cs.miami.edu/~tptp/): Thousands of Problems for Theorem Provers (Univ. Miami)
- [Benchmark Verification Tasks](https://sv-comp.sosy-lab.org/2013/benchmarks.php): Benchmark verification tasks in software verification, as used in SV-COMP
- [Larry Wos' Notebooks](https://www.automatedreasoning.net/): series of notebooks presenting some of Larry Wos’s most recent and hitherto unpublished research in automated reasoning (also in 1st order logic) ([Argon Nat. Lab](https://en.wikipedia.org/wiki/Larry_Wos))
- [SMT-LIB](http://www.smtlib.org/): benchmarks for SMT
- [DPPD](http://users.ecs.soton.ac.uk/mal/systems/dppd.html): The Dozens of Problems for Partial Deduction (DPPD) Library of Benchmarks aims at being a standard suite of benchmarks for partial deduction (Univ. Dusseldorf)
- [QMLTP](http://www.iltp.de/qmltp/): Quantified Modal Logics Theorem Proving (QMLTP) library provides a platform for testing and benchmarking ATP systems for first-order modal logics (Univ. Potsdam)
- [ILTP](http://www.cs.uni-potsdam.de/ti/iltp/): Intuitionistic Logic Theorem Proving (ILTP) library provides a platform for testing and benchmarking ATP systems for first-order and propositional intuitionistic logic (Univ. Potsdam)
- [asparagus](https://asparagus.cs.uni-potsdam.de/): Environment for submitting and archiving benchmarking Answer-Set Programming (ASP) problems and instances (Univ. Potsdam)
- [TPDB](https://www.lri.fr/~marche/tpdb/): Termination Problems Database of test problems for termination provers: term rewrite systems and logic programs (LRI)
- [CSPLib](https://www.csplib.org/): Benchmark library of problems for constraint solvers (Izmir Univ. Economics, Univ. St Andrews, Univ. New South Wales)
- [OR-library](http://people.brunel.ac.uk/~mastjjb/jeb/info.html): Test data sets for a variety of Operations Research (OR) problems (Imperial College London)
- [SATLIB](http://www.satlib.org/): Benchmark problems, solvers, and tools for SAT related research (TU Darmstadt, Univ. British Columbia)
- [SatEx](https://www.swmath.org/software/1588): Experiments and execution traces of SAT solvers, on all benchmarks that are provided
- [FEVS](http://vsl.cis.udel.edu/fevs/index.html): set of programs designed to be used as a test suite for tools that verify functional equivalence (Univ. of Delaware)


# Abbreviations
- u: unspecified license
- FUSC: Free Under Specific Condition (wikipedia term), usually free for academic/research use
- open: open source license
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
- ?: absent either due to time-constrained browsing (please complete) or not found
