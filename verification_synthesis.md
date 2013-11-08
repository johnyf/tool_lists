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

# Model Checking

## Closed Systems (Everything controlled)

### Explicit
- [SPIN](http://spinroot.com/spin/whatispin.html) (FUSC, C): LTL model checking for closed systems in Promela ([JPL/Caltech](http://lars-lab.jpl.nasa.gov/), Bell Labs)
	* [modex](http://spinroot.com/modex/) (FUSC, C): C -> Promela: model extractor ([JPL/Caltech](http://lars-lab.jpl.nasa.gov/), Bell Labs)
	* [spinja](http://code.google.com/p/spinja/) (Apache, Java): Promela model checker (Univ. Twente, TNO)
	* [HSF-SPIN](http://www.albertolluch.com/research/tools): SPIN directed model checking extension [IMT Lucca]
	* [Promela -> C](http://www.ida.liu.se/~kejia/c2promela/) (OCaml): translator (Uppsala Univ.)
	* [Promela -> C](http://www.mathematik.uni-stuttgart.de/~floeff/publications/96-enstparis-s2-report.pdf): translator (Univ. Stuttgart)
	* [Promela -> Java](http://members.tele2.nl/edwin.v/compiler.html) (?, Java): translator ([TU Delft](http://members.tele2.nl/edwin.v/index.html))
	* [jSpin](http://code.google.com/P/Cjspin/) (GPL-2, Java): GUI for SPIN and Erigone
	* [Erigone](http://code.google.com/p/erigone/) (GPL-2, Ada): partial SPIN re-implementation for educational purposes
	* [EpiSpin](http://epispin.ewi.tudelft.nl/): Eclipse plug-in for editing & verifying Promela using Spin ([TU Delft](http://swerl.tudelft.nl/twiki/pub/Main/PastAndCurrentMScProjects/thesis-bob-de-vos.pdf))
	* [Eclipse Pug-In for SPIN](http://matrix.uni-mb.si/en/science/tools/eclipse-plug-in-for-spin//) (?): (Univ. Maribor, TU Braunschweigin)
	* [st2msc](http://matrix.uni-mb.si/en/science/tools/st2msc-tool/) (?, Java): SPIN trail -> Message Sequence Chart (Univ. Maribor)
	* [Real-Time SPIN](http://www-verimag.imag.fr/~tripakis/rtspin.html): quantitative dense time SPIN extension using Real-Time Promela ([VERIMAG/CNRS](http://www-verimag.imag.fr/~tripakis/index.html))
	* [nano-Promela](https://bitbucket.org/simonhj/nano-promela): tools for nano-Promela language
	* [promela-metamodel](https://code.google.com/p/promela-metamodel/): used to generate Promela from BPEL
	* [Promela library](https://forge.ocamlcore.org/projects/promela/) (BSD-3, OCaml): types for Promela expressions, statements, procs and models as OCaml datastructures, with export to Promela for model checking with SPIN (TU Munchen)
	* [LWAASpin](http://www.pst.ifi.lmu.de/projekte/lwaaspin/) (SPIN's license): SPIN modified to use linear weak alternating automata instead of Buchi automata (Univ. Munchen)
	* [Hugo/RT](http://www.pst.informatik.uni-muenchen.de/projekte/hugo/) (? src by email): XMI | ArgoUML | UTE -> Promela | UPPAAL | KIV | Java | SystemC | Smile machines | UTE model | dot (state machines | interactions) and SPIN | UPPAAL trail -> UML run: UML model translator for model checking, theorem proving, code generation (Univ. Munchen, LORIA/INRIA Nancy)
	* [Pi2Promela](http://lcs.ios.ac.cn/~wp/pi2pro_manual.html) (?, C/Java): compiler from pi-calculus models to Promela, includes GUI ([Chinese Acad. Sciences](http://lcs.ios.ac.cn/~wp/))
- [LTSmin](http://fmt.cs.utwente.nl/tools/ltsmin/) (BSD-3): model checking, LTS minimization, interface to other tools (Univ. Twente)
- [MoonWalker](http://fmt.cs.utwente.nl/tools/moonwalker/) (Apache-2, C#): model check CIL bytecode programs ([Mono .NET](http://www.mono-project.com/Main_Page) platform apps), [MoonWalker src](http://code.google.com/p/moonwalker/)(Univ. Twente)
- [DIVINE-2](http://divine.fi.muni.cz/) (BSD-3): Parallel LTL model checking, [DIVINE](http://divine.fi.muni.cz/darcs/mainline/gui/help/divine/divine-cluster.html) (Masaryk Univ.)
- [PRISM](http://www.prismmodelchecker.org/) (GPL-2): Probabilistic Model Checker: discrete/continuous-time Markov chains, timed automata, etc. (Univ. Birmingham, Univ. Oxford)
- [SPOT](http://spot.lip6.fr/wiki/) (GPL, C++/Python): object-oriented model checking library using TGBA
- [JPF](http://babelfish.arc.nasa.gov/trac/jpf) ([NOSA-1.3](http://javapathfinder.sourceforge.net/NOSA-1.3-JPF.txt)): Java model checking & extensions (NASA Ames)
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

### Symbolic
- [SMV](http://www.cs.cmu.edu/~modelcheck/smv.html) (?): CTL symbolic model checker (CMU)
	* [Cadence SMV](http://www.kenmcmil.com/smv.html) (FUSC): CMU SMV extension: backward compatible more expressive mode description language, synthesizable VERILOG, compositional verification, CTL | LTL | FSA | embedded assertions, GUI (Cadence)
- [NuSMV](http://nusmv.fbk.eu/) (LGPL): Symbolic model checking (FBK, CMU, Univ. Genoa, Univ. Trento)
	* [NuGAT](https://es.fbk.eu/index.php?n=Tools.NuGaT) (LGPL-2+): Game solver on top NuSMV
- [jStar](http://www.jstarverifier.org/) (BSD-3, OCaml): (Queen Mary Univ. London, Cambridge Univ., ETH)
- [coreStar](https://github.com/seplogic/corestar) (BSD-3, OCaml): symbolic execution engine for analysis and verification with separation logic (Queen Mary Univ. London, Univ. Cambridge)
- [JSCert JuS](http://jscert.org/index.html): Certified JavaScript (Imperial College, INRIA)
	* [jabstr](https://github.com/MatkoBotincan/jabstr) (LGPL, Ocaml): jStar plugin for numerical abstractions
- [LStar](https://bitbucket.org/jvillard/lstar/wiki/Home) (BSD-3, OCaml): automatic prover for programs written in bitcode using separation logic (UCL)
- [VIS](http://vlsi.colorado.edu/~vis/): logic circuit simulation, circuit verification, fair CTL model checking, logic synthesis via hierarchy restructuring [UC Berkeley, Univ. Colorado at Boulder, Univ. Texas at Austin]
- [KIND](http://clc.cs.uiowa.edu/Kind/) (BSD-3, OCaml): K-induction based for safety properties of Lustre programs, Automatic invariant generation, parallel: PKIND (Univ. Iowa, NASA/CMU, ONERA)
- [VerICS](http://verics.ipipan.waw.pl/start) (FUSC, Java): SAT verification of timed & multi-agent systems modeled by networks of communicating automata (Polish Academy of Sciences)
- [Augur 2](http://www.ti.inf.uni-due.de/research/tools/augur2/) (GPL-2, C++): verification of systems described by (attributed) graph transformations using approximated unfoldings ([Univ. Duisburg-Essen](http://www.ti.inf.uni-due.de/people/koenig/))
- [Mercury](http://rodrigotaclasaad.drupalgardens.com/content/mercury): Parallel Local Sub-CTL Model Checking [LAAS-CNRS]
- [Boogie](http://research.microsoft.com/en-us/projects/boogie/) ([Ms-PL](http://boogie.codeplex.com/license), F#/C#): Intermediate verification language, intended as a layer on which to build program verifiers for other languages (Microsoft Research)
	* [SymDiff](http://research.microsoft.com/en-us/projects/symdiff/default.aspx): Language-independent differential program analysis (C, Boogie front-ends available) (Microsoft Research)
- [VCC](http://research.microsoft.com/en-us/projects/vcc/default.aspx) ([FUSC](http://vcc.codeplex.com/license), F#/C#/C/Perl): annotated concurrent C programs (Microsoft Research)
- [HAVOC](http://research.microsoft.com/en-us/projects/havoc/default.aspx) (?): for C in the presence of pointer manipulations, unsafe casts and dynamic memory allocation (Microsoft Research)
- [Dafny](http://dafny.codeplex.com/) ([Ms-PL](http://dafny.codeplex.com/license), C#): imperative object-based language with built-in specification constructs and static program verifier for functional correctness ([Microsoft Research](http://research.microsoft.com/en-us/um/people/leino/))
- [Spec\#](http://specsharp.codeplex.com/) ([FUSC](http://specsharp.codeplex.com/license), C#): Object-oriented .NET programming language with design-by-contract features for method pre-/postconditions & object invariants, non-null type system (Microsoft Research)
- [Whiley](https://github.com/DavePearce/Whiley) (BSD-3, Java/C/): Object-oriented and functional programming language with static checking, including: divide-by-zero, array out-of-bounds and null dereference errors ([Victoria Univ. of Wellington](http://homepages.ecs.vuw.ac.nz/~djp/))
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
- [TLA+](http://research.microsoft.com/en-us/um/people/lamport/tla/toolbox.html) (MIT, Java/Eclipse/C-like): IDE for TLA+ tools ([Microsoft Research](http://research.microsoft.com/en-us/um/people/lamport/))
	* [TLA+ Tools](http://research.microsoft.com/en-us/um/people/lamport/tla/tools.html) (MIT, Java/C-like): Included in TLA+ toolbox, but this is cmd-line version [TLC](http://research.microsoft.com/en-us/um/people/lamport/tla/tlc.html) (MIT, ?): MC for TLA+ (Temporal Logic of Actions, Lamport), included in TLA+ tools ([Microsoft Research](http://research.microsoft.com/en-us/um/people/lamport/))
		+ [SANY](http://research.microsoft.com/en-us/um/people/lamport/tla/sany.html) (MIT, Java): Parser & semantic analyzer for TLA+ ([Microsoft Research](http://research.microsoft.com/en-us/um/people/lamport/))
		+ [TLC](http://research.microsoft.com/en-us/um/people/lamport/tla/tlc.html) (MIT, ?): MC and simulator for subclass of "executable" TLA+ (Temporal Logic of Actions, Lamport) ([Microsoft Research](http://research.microsoft.com/en-us/um/people/lamport/))
		+ [PlusCal](http://research.microsoft.com/en-us/um/people/lamport/tla/pluscal.html) (MIT, C-like): Translator from the PlusCal algorithm language to TLA+ ([Microsoft Research](http://research.microsoft.com/en-us/um/people/lamport/))
		+ [TLATeX](http://research.microsoft.com/en-us/um/people/lamport/tla/tlatex.html) (MIT, Java): Program for typesetting TLA+ specs ([Microsoft Research](http://research.microsoft.com/en-us/um/people/lamport/))
	* [TLAPS](http://tla.msr-inria.inria.fr/tlaps/content/Home.html) (BSD-2, OCaml/C/Perl): MC for TLA+ using: Zenon | Isabelle (INRIA/Microsoft)
- [CRefine](http://www.cs.york.ac.uk/circus/tools/refinement.php) (?, Java): Verifies `Circus` specs purely by applying various well-proved refinement laws, requires veriT (Univ. York)
- [UTP and Cirus Theories in ProofPower-Z](http://www.cs.york.ac.uk/circus/tools/utp.php) (?, ?): embedding the theories (relations, designs, reactive processes) of UTP in the theorem prover ProofPower-Z, formal proofs can be mechanically constructed (Univ. York)
- [Circus Type Checker](http://www.cs.york.ac.uk/circus/tools/type.php) (? , Java): Syntax type checker for Circus specifications (Univ. York, UFPCI)
- [JCircus](http://www.cs.york.ac.uk/circus/tools/jcsp.php) (?, Java): Automatically translate Circus programs into Java, for the purpose of animation and simulation (Univ. York)
- [ClawCircus](http://www.cs.york.ac.uk/circus/tools/control.php) (?, Java): Java-based tools primarily for generating Circus models from Simulink (Univ. York)
- [Circus Parser](http://sourceforge.net/projects/czt/) (GPL-2, Java): Included in Community Z tools (Univ. York)
- [Rodin](http://www.event-b.org/) (EPL, Eclipse): Eclipse-based platform for refinement and mathematical proof of Event-B (Univ. Southampton)

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
- [LTSA](http://www.doc.ic.ac.uk/~jnm/book/ltsa/LTSA_applet.html) (?, Java): Labelled Transition System Analyzer ([Imperial College London](http://www-dse.doc.ic.ac.uk/cgi-bin/moin.cgi/jnm))

### LTL -> DRA
- [ltl2dstar](http://www.ltl2dstar.de/) (GPL): LTL -> DRA (deterministic Rabin) ([Univ. Bonn](http://www.ltl2dstar.de/literature/ltl2dstar-diploma-thesis.pdf))
	* [online interface](http://www.cds.caltech.edu/~slivings/sandbox/wrapltl.php) ([Caltech.CDS](http://scottman.net/))

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
	* [AMoRE](http://amore.sourceforge.net/) (GPL-2, C/Java): Automata, Monoids, and Regular Expressions (RWTH AaachenUniv., Univ. Kiel)
	* [libmVCA]
	* [liblangen]
	* [finite automata tool]
- [APHMIN](http://depend.cs.uni-sb.de/tools/aphmin/) (?, ?): Tools to generate, manipulate, and minimize acyclic phase-type representations (Saarland Univ.)
- [FlowSim](http://depend.cs.uni-sb.de/tools/flowsim/) (GPL-3, ?): Measure resources needed to find maximal strong simulation relation for a model under different optimizations (Saarland Univ.)
- [fc2symbmin](http://www-sop.inria.fr/meije/personnel/Michel.Bourdelles/tutorial.html#Section1): Finite State Mealy Machine analyzer (INRIA)

## Open Systems (Games: System & UnControlled Environment)
- [TuLiP](www.cds.caltech.edu/tulip) (BSD-3, Python): Receding Horizon Temporal Logic Planning Toolbox ([Caltech.CDS](http://www.cds.caltech.edu/~murray/wiki/Main_Page))
	* [gr1c](http://slivingston.github.io/gr1c/) (BSD-3, C): checking realizability of and synthesizing strategies for GR(1) specifications & much more ([Caltech.CDS](http://scottman.net/))
- [LTLMoP](http://ltlmop.github.io/) (GPL-3, Python): designing, testing, and implementing hybrid controllers generated automatically from task specifications written in Structured English or Temporal Logic ([Cornell](http://cornell-asl.org/wiki/index.php?title=Main_Page))
	* [slugs](https://github.com/LTLMoP/slugs) (BSD-3, C++): a stand-alone reactive synthesis tool for GR(1) synthesis (Cornell)
- [Tools from Boston Univ.](http://hyness.bu.edu/Software.html) (?, MATLAB)
- [Tools from Saarland University](http://react.cs.uni-sb.de/tools/) (Saarland Univ.)
- [PESSOA](https://sites.google.com/a/cyphylab.ee.ucla.edu/pessoa/home) (FUSC, MATLAB): synthesis of correct-by-design embedded control software based on approximate bisimulations (UCLA)
- [TALIRO](https://sites.google.com/a/asu.edu/s-taliro/) (GPL, MATLAB) ([ASU](http://www.public.asu.edu/~gfaineko/))
- [Anzu](http://www.iaik.tugraz.at/content/research/design_verification/anzu/) (Perl): synthesizes Verilog from LTL ([TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
- [RATSY](http://rat.fbk.eu/ratsy/) (LGPL-2+, Python/PyGTK): PSL | BA specs -> gr1 synthesis, game-based debug approach, circuit synthesis ([TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
	* [RAT](http://rat.fbk.eu/) (?, Python): RATSY's pedecessor (FBK, [TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
- [GIST](http://pub.ist.ac.at/gist/index.html) (?): solving probabilistic games with ω-regular objectives qualitatively (IST Austria)
- [JTLV](http://sourceforge.net/projects/jtlv/) (LGPL-2, Java/C), [TLV](http://www.cs.nyu.edu/acsys/tlv/)
- [GAVS+](http://www6.in.tum.de/~chengch/gavs/) (GPL-3, Java): visualize algorithmic games used in verification and synthesis (TU Munchen)
- [PGSolver](http://www2.tcs.ifi.lmu.de/pgsolver/) (OCaml): tools for generating, manipulating and solving parity games (Univ. Muchich, Univ. Kassel)
- [Acacia+](http://lit2.ulb.ac.be/acaciaplus/) (GPL, Python/C): LTL Realizability check & winning strategy synthesis using AntiChains [repo](https://code.google.com/p/ltlsynthesis/) (Univ. Mons), [Acacia](http://lit2.ulb.ac.be/acacia/) (GPL-2, Perl)
- [Lily](http://www.iaik.tugraz.at/content/research/design_verification/lily/) (Perl): synthesizes from PSL | LTL & I/O signal partition, works on top of Wring, outputs VERILOG | dot (TU Graz)
- [Quasy](http://pub.ist.ac.at/quasy/): Quantitative synthesis of reactive systems from qualitative & quantitative GOAL specs, in/out: GOAL format (IST Austria)
- [CADP](http://www.inrialpes.fr/vasy/cadp.html) (FUSC): compilers, equivalence checking tools, model-checkers for temporal logics & μ-calculus, verifications: enumerative, on-the-fly, symbolic using BDD, etc. (INRIA)
- [PDSolver](http://www.cs.ox.ac.uk/matthew.hague/pdsolver.html) (OCaml): evaluating both mu-calculus formulas over pushdown systems and pushdown parity games (Oxford Univ.)
- [Mica](http://www.irisa.fr/s4/tools/mica/Mica__A_Modal_Interface_Compositional_Analysis_Library/Introduction.html) (CeCILL-C-1, OCaml):  Modal Interface algebra for contract based design ([INRIA/IRISA](http://www.irisa.fr/prive/Benoit.Caillaud/Benoit_Caillauds_Professional_homepage/Welcome.html))
- [Esterel](http://en.wikipedia.org/wiki/Esterel), [old](http://www-sop.inria.fr/meije/esterel/esterel-eng.html): Synchronous reactive programming language & compiler to FSM (C language), Graphical symbolic debugger, explicit/BDD verification for bisimulation reduction | safety checking (Ecole des Mines de Paris, INRIA)
	* [CEC](http://www1.cs.columbia.edu/~sedwards/cec/) (BSD-3, C++/ANTLR): Esterel V5 compiler to C | Verilog | BLIF ([Columbia](http://www.cs.columbia.edu/~sedwards/))
	* [scdata](http://www-sop.inria.fr/meije/esterel/scdata.html) (?): Boolean datapath generator for Esterel: translates action calls in sc code over boolean variables into standard nets also in sc (INRIA, Ecole des Mines de Paris)
	* [Ocjava](http://www-sop.inria.fr/meije/esterel/ocjava.html) (?): Esterel Java code generator (INRIA)
- [Xeve](http://www-sop.inria.fr/meije/verification/Xeve/): Esterel verification environment (INRIA)
- [Lustre](http://en.wikipedia.org/wiki/Lustre_%28programming_language%29): Declarative, synchronous dataflow programminglanguage for reactive systems
	* [MATOU](http://www.cfdvs.iitb.ac.in/download/Docs/verification/tools/kronos/Verimag_Home_Page/PEOPLE/Florence.Maraninchi/MATOU/index.phtml) (?): Implementation of mode-automata on top of Lustre (VERIMAG)
- [NBAC](http://pop-art.inrialpes.fr/~bjeannet/nbac/index.html) (OCaml): Co-/Reachability, slicing of synchronous deterministic reactive systems with Boolean, numerical variables (VERIMAG)
	* [`lus2nbac`](http://pop-art.inrialpes.fr/~bjeannet/nbac/index_6.html): Convert Lustre to NBAC (VERIMAG)
	* [`nbac2lucky`](http://pop-art.inrialpes.fr/~bjeannet/nbac/index_7.html): Convert counterexamples to Ludic debugger (VERIMAG)
	* [`autoc2auto`, `auto2nbac`, `nbac2auto`](http://pop-art.inrialpes.fr/~bjeannet/nbac/index_8.html):  Analyze AUTOC/AUTO hybrid automata (VERIMAG)
- [SIGNAL](http://en.wikipedia.org/wiki/SIGNAL_programming_language): Synchronized data-flow programming language for systems with multiple clocks ([INRIA](http://www.irisa.fr/espresso/home_html))
	* [Polychrony / SME](http://www.irisa.fr/espresso/Polychrony/) (GPL, Eclipse Public License): SIGNAL IDE (IRISA)
- [SyncCharts](http://en.wikipedia.org/wiki/SyncCharts): Graphical formalism for reactive modeling ([Univ. Nice Sophia-Antipolis](http://www-sop.inria.fr/members/Charles.Andre/))
	* [SPORTS Project](http://www.i3s.unice.fr/~map/WEBSPORTS/SyncCharts/) (FUSC): SyncCharts tools
	* [SCC](http://julien.boucaron.free.fr/i3s/)): SyncCharts Compiler Collection for XML | BLIF | C output (Univ. Nice Sophia-Antipolis, INRIA)
- [Sigali](http://www.irisa.fr/vertecs/Softwares/sigali.html), [old](http://www.irisa.fr/vertecs/Logiciels/sigali.html) (FUSC): Model check implicit labeled transition systems (INRIA)
- [TGV](http://www.irisa.fr/vertecs/Softwares/TGV.html) (?): Generation of conformance test suites for protocols, based on I/O transition systems (IOLTS) (IRISA)
- [Averest](http://en.wikipedia.org/wiki/Averest): Synchronous programming language and compiler to TS, symbolic model checker, tool for hardware/software synthesis ([TU Kaiserslautern](http://es.informatik.uni-kl.de/))
- [Times](http://www.timestool.com/) (?): Tool for Modeling & Implementation of Embedded Systems (GUI editor, simulator, verifier for schedulability analysis) (Uppsala Univ.)
- [BigMC](https://github.com/bigmc/bigmc) (GPL, C++/C/PHP/...): Bigraphical reactive systems (IT Univ. Copenhagen)
- [Mocha](http://mtc.epfl.ch/software-tools/mocha/) (BSD, Java | C/Tcl/Tk): Interactive environment for system specification (reactive modules language), execution (randomized, guided, mixed), requirement specification (Alternating Temporal Logic, superset of CTL), ATL MC, implementation verification (EPFL, UC Berkeley, UPenn, SUNYSB)
- [Ticc](http://code.google.com/p/ticc/) (GPL-2, ?): Interface compatibility and composition, components specify own behavior and that expected by others, CTL properties checked and propagated (UCSC)

## Harel StateCharts
- [PlayGo](http://www.weizmann.ac.il/mediawiki/playgo/index.php/Main_Page) (Weizmann Inst.)
- [Time Rover](http://www.time-rover.com/)
 
# Hybrid Systems
- [Ptolemy](http://ptolemy.eecs.berkeley.edu/index.htm) (BSD-3, Java): modeling, simulation, and design of concurrent, real-time, embedded systems (UC Berkeley)
- [HyTech](http://embedded.eecs.berkeley.edu/research/hytech/) (FUSC, C): computes condition under which a linear hybrid system satisfies a temporal requirement (UC Berkeley)
- [HyLink](http://hsver.crhc.illinois.edu/index.php/HyLink) (closed, MATLAB): Translates restricted class of Simulink/Stateflow models to hybrid automata (UIUC)
- [d/dt](http://www-verimag.imag.fr/~tdang/ddt.html) (?, ?): Reachability analysis of Continuous and Hybrid Systems with differential inclusions ([VERIMAG](http://www-verimag.imag.fr/~tdang/))
- [HARE](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HARE) (?): Abstraction refinement for safety
- [HTV](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HTV) (closed, MATLAB): verify systems from their simulation and run-time traces using imprecise samples and possibly incomplete models to compute overapproximations of bounded reach sets (UIUC)
- [START](http://www.andrew.cmu.edu/user/arieg/Rek/): time-bounded static analysis of concurrency properties of Real-Time Embedded Software
- [IF](http://www-verimag.imag.fr/~async/IF/index.html) (FUSC): static analysis, model-checking, test generation, [Open-Kronos](http://www-verimag.imag.fr/~tripakis/openkronos.html), [Kronos](http://www-verimag.imag.fr/DIST-TOOLS/TEMPO/kronos/): TCTL verification of Timed Automata (VERIMAG)
- [UPPAAL](http://www.uppaal.org/), [UPPAAL-Tiga](http://people.cs.aau.dk/ ̃adavid/tiga/) (FUSC): Timed automata (Uppsala Univ., Aaalborg Univ.)
	* [manipulate UPPAAL XML](https://launchpad.net/pyuppaal) (GPL-3, Python)
	* [Yggdrasil](http://www.quasimodo.aau.dk/tools.html) (?, ?): UML (subset) -> Uppaal, intended for test generation (Aaalborg Univ.)
	* [METAMOC](http://metamoc.dk/) (GPL-3, Python): WCET Analysis of ARM Processors using Real-Time model-checking (Aalborg Univ.)
	* [SARTS](http://www.sarts.dk/old.php) (?, Java): Model Based Schedulability Analysis of Real-Time Systems, SCJ2, UPPAAL (Aaalborg Univ.)
- [OPAAL](https://launchpad.net/opaal) (GPL-3, Python): distributed/parallel (discrete time) model checker for networks of timed automata  using MPI
- [ECDAR](http://people.cs.aau.dk/~adavid/ecdar/) (FUSC): timed interface theory (Aaalborg, INRIA, ITU)
- [PyECDAR](https://project.inria.fr/pyecdar/) (GPL-2, Python): solve timed games based on timed automata models (ITU)
- [SpaceEx](http://spaceex.imag.fr/) (GPL-3, C++): Reachability & safety verification (Verimag,  	Lab Jean Kuntzmann, DGA-MI)
- [PHAVer](http://www-verimag.imag.fr/~frehse/phaver_web/) (GPL-2, C++): verifying safety properies of hybrid systems (exact arithmetic, on-the-fly over-approximation of PWA dynamics, compositional & assume-guarantee reasoning) ([Verimag](https://sites.google.com/site/frehseg/))
	* [vim highlight](http://www.vim.org/scripts/script.php?script_id=3256), its [github](https://github.com/vim-scripts/phaver)
	* [ProHVer](http://depend.cs.uni-sb.de/tools/prohver/) (GPL-3, C++): Unbounded reachability probability for probabilistic hybrid automata (Univ. Saarland)
- [ATAS](http://sourceforge.net/projects/atao/) (GPL-3, Python): Alternating 1-clock (fully decidable) Timed Automata Solver
- [CIF](http://se.wtb.tue.nl/sewiki/cif/start): Compositional Interchange Format for Hybrid Systems toolset
- [CheckMate](http://www.mathworks.com/matlabcentral/fx_files/15441/3/content/doc/main.htm) (MATLAB) modeling, simulation & investigation, [demos](http://www.mathworks.com/matlabcentral/fileexchange/17004-checkmate-demos)
- [PPL binding](https://launchpad.net/pyppl) (GPL-2, Python): for [Parma Polyhedral Lib](http://bugseng.com/products/ppl) features some specific methods for Timed Automata analysis
- [Passel](http://publish.illinois.edu/passel-tool/) (closed, C#/Python): invariant synthesis and inductive invariant proving (UIUC)
- [IOA](http://groups.csail.mit.edu/tds/ioa/) (MIT, Java): I/O automata formal language (MIT)
- [TEMPO](http://www.veromodo.com/) (closed, Java): Formal language for modeling distributed systems w/ | w/o timing constraints as collections of interacting state machines, i.e., timed input/output automata (TIOA) (UIUC)
	* [Tempo2HSal](http://www.csl.sri.com/users/tiwari/VVFCS.html) (?, Python): Tempo (`.tioa`) -> HybridSAL (`.hsal`) translator (SRI)
- [Ariadne](http://trac.parades.rm.cnr.it/ariadne/) (GPL-3, C++/Python): dynamical systems set-based analysis (reachability analysis, robust simulation, safety verification - reset, flow, guard predicates given by nonlinear functions) (Univ. Udine, PARADES, CWI, Univ. Verona)
- [AMC](http://symbolaris.com/info/amc.html) (?, Mathematica): model checker for non-linear hybrid systems based on the abstraction refinement framework (CMU, Univ. Oldenburg)
- [SAAtRE](http://symbolaris.com/info/saatre.html) (?): Abstraction refinement model checker for Timed Automata based on extended SAT-solving, UPPAAL-like input format (Univ. Oldenburg, CWI)
- [HybridSal](http://sal.csl.sri.com/hybridsal/) (GPL-2, LISP/Java): Language extension to SAL for specifying Hybrid Systems & hybrid abstraction tool to discrete SAL specifications for model checking with other SAL tools (SRI)
- [Rabbit](http://www.sosy-lab.org/~dbeyer/Rabbit/) (Apache): RTS modular spec: timed (and hybrid) automata: CottbusTimed Automata, MC for reachability analysis and refinement check (Bradenburg TU)
- [HSolver](http://hsolver.sourceforge.net/) (LGPL): based on RSOLVER constraint solver, correctness does not depend on floating point rounding errors, handles non-linear ODEs ([Academy of Sciences Czech Republic](http://www2.cs.cas.cz/~ratschan/))
- [Fortuna](http://www.cs.ru.nl/J.Berendsen/fortuna/) (GPL-3, C++/Eclipse): MC priced probabilistic timed automata (PPTAs) (Univ. Twente)
- [MoToR](http://depend.cs.uni-sb.de) (GPL, ?): Macro-preprocessor for MoDeST, a stochastic real-time systems formalism, interfacing to UPPAAL, CADP, Eclipse, Mobius (Univ. Saarlandes)
	* [Eclipse plugin](http://depend.cs.uni-sb.de/index.php?446) (Univ. Saarlandes)
- [Mobius](https://www.mobius.illinois.edu/) (?, Java/C++): Model-based environment for validation of system reliability, availability, security, and performance ([UIUC](https://www.perform.csl.illinois.edu/))
- [MCPTA](http://www.modestchecker.net/) (FUSC, ?): Probabilistic Timed Automata model checker for MoDeST | UPPAAL | PRISM - maps on PRISM (Saarland Univ.)
- [MRMC](http://www.mrmc-tool.org/trac/) (GPL-3, C): MC for: Discrete/Continuous Markov Chains, Reward models, decision processes (Univ. Twente, RWTH Aachen)
- [PASS](http://depend.cs.uni-sb.de/tools/pass/) (bin, ?): CEGAR MC for infinite-state probabilistic models, MDPs (Saarland Univ.)
- [INFAMY](http://depend.cs.uni-sb.de/tools/infamy/) (bin, ?): CSL Model Checker for infinite-state Markov chains - CTMCs (Saarland Univ.)
- [PARAM](http://depend.cs.uni-sb.de/tools/param/) (GPL-3, C++): Reachability probability computation for parametric Markov chains - DTMCs (Saarland Univ.)
- [pyHybridAnalysis](http://www.dmi.units.it/~casagran/pyHybridAnalysis/) (LGPL-3, Python): ε-semantics reachability ([VERIMAG](http://www-verimag.imag.fr/~dreossi/publications.html))

# Theorem Provers
- [Automath](https://en.wikipedia.org/wiki/Automath) (?, ?): One of the first formal proof languages and proof checker ([Eindhoven Univ.](https://en.wikipedia.org/wiki/Nicolaas_Govert_de_Bruijn))
	* [Modern Automath implementation](http://www.cs.ru.nl/~freek/aut/) (?, C): Languages AUT-68, AUT-QE ([Radboud Univ. Nijmegen](http://www.cs.ru.nl/~freek/index.html))
- [PVS](http://pvs.csl.sri.com/), its [github](https://github.com/samowre/PVS.git) (GPL-3, Common LISP/C/Emacs LISP/etc): Specification language & TP, based Church's type theory extended with dependent types (SRI)
- [TPS](http://gtps.math.cmu.edu/tps.html): (CMU)
- [Coq](http://coq.inria.fr/) (INRIA, Ecole Polytechnique, Paris-Sud 11 Univ., Paris Diderot Univ., CNRS)
- [Isabelle](http://www.cl.cam.ac.uk/research/hvg/Isabelle/) (BSD): (Univ. Cabridge, TU Munchen, Univ. Paris-Sud)
- [HOL](http://www.cl.cam.ac.uk/research/hvg/HOL/): Iterative Theorem proving in higher-order logic (Univ. Cambridge)
- [HOL-omega](http://trustworthytools.com/id17.html)
- [ALF](http://www.cse.chalmers.se/research/group/logic/alf/guide.html) (Univ. Goterborg/Chalmers)
- [Alfa](http://www.cse.chalmers.se/~hallgren/Alfa/): successor of ALF
- [Agda](http://wiki.portal.chalmers.se/agda/pmwiki.php)
- [ACL2](http://www.cs.utexas.edu/users/moore/acl2/): part of Boyer-Moore family of provers (Univ. Texas at Austin)
	* [Nqthm](http://en.wikipedia.org/wiki/Nqthm) (GPL-2, ?): Boyer–Moore TP using Pure LISP variant, precursor to ACL2 (Univ. Texas, Austin)
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
- [SAL](http://sal.csl.sri.com/) (GPL-2, C): Language for specifying concurrent systems in a compositional way. BDD-based & SAT-based MC, experimental "Witness" MC, "infinite" bounded MC based on SMT solving, simulator, deadlock checker, automated test generator (SRI, Stanford, Berkeley)
- [Mizar](http://mizar.org/)
- [NuPRL](http://www.nuprl.org/): Formal Digital Library (Cornell)
- [MetaPRL](http://www.cs.cornell.edu/jyh/metaprl/default.html)
- [Gandalf](http://deepthought.ttu.ee/it/gandalf/)
- [E-SETHEO](http://www4.informatik.tu-muenchen.de/~schulz/WORK/e-setheo.html): strategy-parallel compositional theorem prover for first-order logic with equality
- [SPASS](http://www.spass-prover.org/): First-Order Logic with Equality (Max Planck Inst. Inf.)
- [Omega](https://code.google.com/p/omega/) (BSD-3): cross between a purely functional programming language and a theorem prover
- [wikipedia list](https://en.wikipedia.org/wiki/Automated_theorem_proving)
- [this thread](http://cs.stackexchange.com/questions/868/types-of-automated-theorem-provers)
- [jImp](http://symbolaris.com/logic/jImp.html) (binary, Java): based on set of support and ordered resolution for first-order logic, supports: clause indexing techniques, subsumption, and tautology elimination, Davis-Putnam-Loveland-Logemann (DPLL) inference procedure (CMU)
- [QEPCAD](http://www.usna.edu/CS/~qepcad/B/QEPCAD.html) (BSD-like, C): Quantifier elimination by partial cylindrical algebraic decomposition (US Naval Academy, Drexel Univ., North Carolina State Univ.)
	* [Mac OS X 10.6, 10.7 binaries](http://www.cl.cam.ac.uk/~lp15/papers/Arith/qepcad-for-mac.html) (Cambridge Univ.)
- [Zenon](http://focal.inria.fr/zenon/) (BSD-3, OCaml): (INRIA)
- [E](http://www4.informatik.tu-muenchen.de/~schulz/E/E.html) (GPL-2, C): Full first-order logic with equality ([TU Munchen](http://www4.in.tum.de/~schulz/Stephan_Schulz/Stephan_Schulz.html))
- [Community Z Tools](http://czt.sourceforge.net/) (GPL-2, Java): Tools for editing, typechecking and animating Z specifications and related notations, including Java framework for building formal methods tools (Univ. Oxford, contrib)
- [ProofPower](http://www.lemma-one.com/ProofPower/index/) (GPL, ?): Tool suite supporting specification and proof in HOL and Z notation (Lemma 1 Ltd)
- [ClawZ](http://www.lemma-one.com/clawz_docs/clawz_docs.html) (?, ?): Simulink -> Z notation (Lemma 1 Ltd)
- [Waldmesiter](http://www.waldmeister.org/index.htm) (FUSC, ?): TP for unit equational logic (Max Planck Inst. Informatik)
- [Spear](http://www.domagoj-babic.com/index.php/ResearchProjects/Spear)
- [Metamath](http://us.metamath.org): Tiny language based on ZFC, and also database of proved theorems

## SAT
- [zChaff](http://www.princeton.edu/~chaff/zchaff.html) (Princeton Open Source): Chaff algorithm ([Princeton](http://www.princeton.edu/~chaff/))
- [MiniSat](http://minisat.se/) and its [github](https://github.com/niklasso/minisat) (MIT, C++/C): minimalistic high-performance solver to help get started ([Chalmers Univ.](http://minisat.se/Authors.html))
	* [qmaxsat](https://sites.google.com/site/qmaxsat/) (MIT, C/C++): Q-dai MaxSAT Solver, based on MiniSat
	* [MiniMarch](http://www.st.ewi.tudelft.nl/sat/minimarch.php)
- [SATABS](http://www.cprover.org/satabs/) (BSD, C): ANSI-C, C++ verification via Boolean program abstraction (Univ. Oxford, Imperial College, Univ. Lugano, CMU)
- [Boppo](http://www.cprover.org/boppo/) (?): MC for Boolean programs featuring: POR, Fixpoint detection using QBF, support for `constraint` construct (Univ. Oxford, Microsoft Research, Univ. Lugano, CMU)
- [CSIsat](http://www.sosy-lab.org/~dbeyer/CSIsat/) (Apache): Interpolating decision procedure for the quantifier-free theory of rational linear arithmetic and equality with uninterpreted function symbols (EPFL, SFU)
- [MSUnCore](http://logos.ucd.ie/wiki/doku.php?id=msuncore): solving (Weighted) (Partial) Maximum Satisfiability (MaxSAT)
- [antom](https://projects.informatik.uni-freiburg.de/projects/antom) (C++): Lib solving: SAT, Unweighted MaxSAT, Partial MaxSAT, \#SAT (Uni. Freiburg)
- [SCIP](http://scip.zib.de/): Mixed int programming (MIP), constraint int programming and branch-cut-and-price
	* [scip-maxsat](https://github.com/msakai/scip-maxsat) (ZIB, C++): Max-SAT frontend for SCIP
- [GLPK](http://www.gnu.org/software/glpk/)
	* [MaxSAT frontend](https://github.com/msakai/glpk-maxsat) for GLPK
- [Lingeling, Plingeling, Treengeling](http://fmv.jku.at/lingeling/)
- [PicoSAT](http://fmv.jku.at/picosat/) (MIT, C)
	* [Python bindings](https://pypi.python.org/pypi/pycosat) (MIT, Python)
- [PrecoSAT](http://fmv.jku.at/precosat/) (MIT-like)
- [RSat](http://reasoning.cs.ucla.edu/rsat/home.html)
- [UBCSAT](http://www.satlib.org/ubcsat/): (Univ. British Columbia)
- [fss](http://dudka.cz/fss) (GPL-3, C++/GAlib): Genetic algorithms
- [QBF Solvers](http://www.cs.toronto.edu/~fbacchus/qbf.html#PreQuel) (C++)
- [MiFuMaX](http://sat.inesc-id.pt/~mikolas/sw/mifumax/) (GPL-3)
- [Shaowei Cai solvers](http://shaoweicai.net/research.html)
- [algorithms](https://github.com/msakai/toysolverw)
- [WBO](http://sat.inesc-id.pt/wbo/): Weighted Boolean Optimization Solver that extends Weighted-Partial Max-SAT and Pseudo-Boolean Optimization
- [PWBO](http://sat.inesc-id.pt/pwbo/)
- [Sat4j](http://www.sat4j.org/) (LGPL, Java)
- [ToulBar2](https://mulcyber.toulouse.inra.fr/projects/toulbar2/) (GPL, C++): weighted constraint satisfaction solver (INRA)
- [march](http://www.isa.ewi.tudelft.nl/sat/march.htm): DPLL with lookahead heuristics (TU Delft)
- [march_eq](http://www.st.ewi.tudelft.nl/sat/march_eq.htm): (TU Delft)
- [march_dl](http://www.st.ewi.tudelft.nl/sat/march_dl.php): (TU Delft)
- [CryptoMiniSat](http://www.msoos.org/cryptominisat2/), its [github](https://github.com/msoos/cryptominisat) (LGPL, C++/C/etc)
- [WinSAT](http://www.mqasem.net/sat/winsat/)
- [HyperSAT](http://www.domagoj-babic.com/index.php/ResearchProjects/HyperSAT): Experiment with B-cubing search space pruning

## SMT
- [Z3](http://z3.codeplex.com/) ([FUSC](http://z3.codeplex.com/license), C++/Python): `.smt2`, `.dimacs`, `.cnf`, `.dl`, `.smt` (Microsoft Research)
- [iZ3](http://rise4fun.com/iZ3) ([FUSC](http://z3.codeplex.com/license), C++/Python): Interpolating, supports: arithmetic, arrays, uninterpreted functions, and quantifiers (Microsoft Research)
- [Boolector](http://fmv.jku.at/boolector/) (GPL-3): bit-vectors and arrays (Johannes Kepler Univ. Linz, Upper Austrian Univ. of Applied Sciences)
- [MathSAT](http://mathsat.fbk.eu/download.html) (FUSC, C++, Python/Java bindings): Theories: equality and uninterpreted functions, linear arithmetic, bit-vectors, and arrays, and Functionalities: computation of Craig interpolants, extraction of unsatisfiable cores, generation of models and proofs, and the ability of working incrementally (FBK, Univ. Trento)
- [SMT-LIB](http://www.cprover.org/SMT-LIB-LSM/) (?, C++): format for Finite lists, sets, maps (Oxford Univ.)
- [veriT](http://www.verit-solver.org/) (BSD-2, C/C++): Complete for quantifier-free formulas with uninterpreted functions and difference logic on real numbers and integers (INRIA, Nancy Univ., UFRN, CNPq, Loria)
	* [haRVey](http://harvey.loria.fr/) (LGPL/BSD-2, C/C++): Predecessor of veriT: haRVey-FOL (LGPL), haRVey-SAT (BSD-2) (INRIA, Nancy Univ., UFRN, CNPq, Loria)	

## Other solvers
- [RSolver]() (LGPL): Quantified inequality constraints ([Academy of Sciences Czech Republic](http://www2.cs.cas.cz/~ratschan/))

# Runtime Verification
- [MOP](http://fsl.cs.illinois.edu/index.php/MOP) (Java): Monitoring-Oriented Programming ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
- [CHIMP](http://www.cs.rice.edu/CS/Verification/Software/software.html): LTL -> monitors: nondeterministic finite-word automata that accept all illegal executions (Rice Univ.)
- [LTL_3](http://ltl3tools.sourceforge.net/) (GPL): LTL -> Moore FSM monitor
- [TOPL](http://rgrig.github.io/topl/) (OCaml): monitor Java programs
- [Breach Toolbox](http://www.eecs.berkeley.edu/~donze/breach_page.html)(BSD-3, MATLAB/C++): Simulation, verification of temporal logic properties and dynamical systems (ODE | Simulink) reachability analysis (UC Berkeley)
- [JTorX](https://fmt.ewi.utwente.nl/redmine/projects/jtorx/wiki/) (?, Java): Model-based testing: Spec: Aldebaran | GraphML | dot | Jararaca | `.sax` | muCRL | `.bcg` | LOTOS, Implementation either these or real program (Univ. Twente)
- [TorX](http://fmt.cs.utwente.nl/tools/torx/introduction.html) (Apache, ?): Conformance testing of reactive software (Univ. Twente, TU Eindhoven, Philips, Lucent)

# Yet un-categorized
- [Maude](http://maude.cs.uiuc.edu/overview.html) (UIUC)
	* [C-Reducer](http://sysma.lab.imtlucca.it/tools/c-reducer/): Automatic c-reduction of object based modules for the Maude system (IMT Lucca)
	* [MESSI](http://sysma.lab.imtlucca.it/tools/ensembles/): Design, validation and performance evaluation of self-assembly strategies with Maude (IMT Lucca)
	* [Circ](http://fsl.cs.illinois.edu/index.php/Circ):  automated behavioral prover based on the circularity principle for Maude ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
- [K](http://www.kframework.org/index.php/Main_Page): rewrite-based executable semantic framework (UIUC)
- [Matching Logic](http://www.matching-logic.org/index.php/Matching_Logic): regard a language through both operational and axiomatic lenses at the same time ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
- [Separation logic & local reasoning](https://wiki.mpi-sws.org/star/ToolSupport): wiki & tools list [Max Planck Inst. for Soft. Sys.](http://www.mpi-sws.org/~viktor/)
- [QMRes](http://www.cs.rice.edu/CS/Verification/Software/software.html): Multi-resolution with ZDDs implementation
- [MTSA](http://sourceforge.net/projects/mtsa/) (Public): Modal Transition Systems Analyser (Imperial College London, Univ. Buenos Aires)
- [FoCs](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.23.9941)

# Other tool lists
- [Wikipedia](https://en.wikipedia.org/wiki/List_of_model_checking_tools)
- [Yahoda](http://anna.fi.muni.cz/yahoda/) [Masaryk Univ.]
- [wikia](http://formalmethods.wikia.com/wiki/VL)
- [UPenn Hybrid System Tools Repository](http://wiki.grasp.upenn.edu/hst/index.php?n=Main.HomePage)
- [VERIMAG Tools](http://www-verimag.imag.fr/Tools,12.html?lang=)
- [verification tools for industrial automation](http://www.chihhongcheng.info/tools)
- [Carloni et al.](http://www.nowpublishers.com/articles/foundations-and-trends-in-electronic-design-automation/EDA-001)
- [Networked Control Systems Repository](http://filer.case.edu/org/ncs/)
- [rise4fun](http://rise4fun.com/)
- [CMU tools](http://www.cs.cmu.edu/~modelcheck/code.htm)
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

# databases
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
- [QBFLIB](http://vlsicad.eecs.umich.edu/BK/Slots/cache/www.qbflib.org/): Collection of benchmark problems, solvers, and tools related to Quantified Boolean Formula (QBF) satisfiability (Univ. Michigan)

# (non-common) abbreviations
- FUSC: Free Under Specific Condition (wikipedia term)
- closed: no source available, common situation: `jar` files
- BA: Buchi Automaton
- GBA: Generalized BA
- TP: Theorem Prover
- ATP: Automatic TP
- RTS: Real-time system(s)
- TU: Technical University
- UT: University of Technology
- EPL: Eclipse Public License
- FOL: First-order logic
- HOL: Higher-order logic
- bin: binary, no sources available/found
- ?: absent either due to time-constrained browsing (please complete) | not found
