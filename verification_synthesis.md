List of verification and synthesis tools.
Please clone, contribute and send pull requests.
Minimal markdown knowledge needed to add links:

`- [Tool name](link url) (license, coded in language): brief description (Institution/other maintainer)`

Please list only Open Source/research tools, proprietary ones are not widely and unconditionally useful.
Conditionally (sufficiently) free tools are welcome.

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
- [LTSmin](http://fmt.cs.utwente.nl/tools/ltsmin/) (BSD-3): model checking, LTS minimization, interface to other tools (Univ. Twente)
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

### Symbolic
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

### LTL -> DRA
- [ltl2dstar](http://www.ltl2dstar.de/) (GPL): LTL -> DRA (deterministic Rabin) ([Univ. Bonn](http://www.ltl2dstar.de/literature/ltl2dstar-diploma-thesis.pdf))
	* [online interface](http://www.cds.caltech.edu/~slivings/sandbox/wrapltl.php) ([Caltech.CDS](http://scottman.net/))

### other
- [dk.brics.automaton](http://www.brics.dk/automaton/): DFA/NFA implementation with UTF16 alphabet & support for (&non-) standard regexp
- [FSA function library](http://users.isr.ist.utl.pt/~pal/cadeiras/deds0708/deds/MatlabFSA.zip) (MATLAB): [doc here](http://users.isr.ist.utl.pt/~pal/cadeiras/deds0708/deds/Projects06-07/BLacerda.pdf) ([ISR-Lisbon](http://users.isr.ist.utl.pt/~blacerda/))

## Open Systems (Games: System & UnControlled Environment)
- [TuLiP](www.cds.caltech.edu/tulip) (BSD-3, Python): Receding Horizon Temporal Logic Planning Toolbox ([Caltech.CDS](http://www.cds.caltech.edu/~murray/wiki/Main_Page))
	* [gr1c](http://slivingston.github.io/gr1c/) (BSD-3, C): checking realizability of and synthesizing strategies for GR(1) specifications & much more ([Caltech.CDS](http://scottman.net/))
- [LTLMoP](http://ltlmop.github.io/) (GPL-3, Python): designing, testing, and implementing hybrid controllers generated automatically from task specifications written in Structured English or Temporal Logic ([Cornell](http://cornell-asl.org/wiki/index.php?title=Main_Page))
	* [slugs](https://github.com/LTLMoP/slugs) (BSD-3, C++): a stand-alone reactive synthesis tool for GR(1) synthesis (Cornell)
- [Tools from Boston Univ.](http://hyness.bu.edu/Software.html) (?, MATLAB)
- [Tools from Saarland University](http://react.cs.uni-sb.de/tools/) (Saarland Univ.)
- [PESSOA](https://sites.google.com/a/cyphylab.ee.ucla.edu/pessoa/home) (FUSC, MATLAB): synthesis of correct-by-design embedded control software based on approximate bisimulations (UCLA)
- [TALIRO](https://sites.google.com/a/asu.edu/s-taliro/) (GPL, MATLAB) ([ASU](http://www.public.asu.edu/~gfaineko/))
- [RATSY](http://rat.fbk.eu/ratsy/) (LGPL-2+, Python): Requirements Analysis Tool with Synthesis
- [GIST](http://pub.ist.ac.at/gist/index.html) (?): solving probabilistic games with ω-regular objectives qualitatively (IST Austria)
- [JTLV](http://sourceforge.net/projects/jtlv/) (LGPL-2, Java/C), [TLV](http://www.cs.nyu.edu/acsys/tlv/)
- [GAVS+](http://www6.in.tum.de/~chengch/gavs/) (GPL-3, Java): visualize algorithmic games used in verification and synthesis (TU Munchen)
- [Anzu](http://www.iaik.tugraz.at/content/research/design_verification/anzu/) (Perl): synthesizes Verilog from LTL ([TU Graz](http://www.iaik.tugraz.at/content/research/design_verification/))
- [PGSolver](http://www2.tcs.ifi.lmu.de/pgsolver/) (OCaml): tools for generating, manipulating and solving parity games (Univ. Muchich, Univ. Kassel)
- [Sigali](http://www.irisa.fr/vertecs/Logiciels/sigali.html) (FUSC): Model check implicit labeled transition systems (INRIA)
- [Acacia+](http://lit2.ulb.ac.be/acaciaplus/) (GPL, Python/C): LTL Realizability check & winning strategy synthesis using AntiChains [repo](https://code.google.com/p/ltlsynthesis/) (Univ. Mons), [Acacia](http://lit2.ulb.ac.be/acacia/) (GPL-2, Perl)
- [Lily](http://www.iaik.tugraz.at/content/research/design_verification/lily/) (Perl): synthesizes from PSL | LTL & I/O signal partition, works on top of Wring, outputs VERILOG | dot (TU Graz)
- [PyECDAR](https://project.inria.fr/pyecdar/) (GPL-2, Python): solve timed games based on timed automata models (ITU)
- [Quasy](http://pub.ist.ac.at/quasy/): Quantitative synthesis of reactive systems from qualitative & quantitative GOAL specs, in/out: GOAL format (IST Austria)
- [CADP](http://www.inrialpes.fr/vasy/cadp.html) (FUSC): compilers, equivalence checking tools, model-checkers for temporal logics & μ-calculus, verifications: enumerative, on-the-fly, symbolic using BDD, etc. (INRIA)
- [PDSolver](http://www.cs.ox.ac.uk/matthew.hague/pdsolver.html) (OCaml): evaluating both mu-calculus formulas over pushdown systems and pushdown parity games (Oxford Univ.)
- [Mica](http://www.irisa.fr/s4/tools/mica/Mica__A_Modal_Interface_Compositional_Analysis_Library/Introduction.html) (CeCILL-C-1, OCaml):  Modal Interface algebra for contract based design ([INRIA/IRISA](http://www.irisa.fr/prive/Benoit.Caillaud/Benoit_Caillauds_Professional_homepage/Welcome.html))

## Harel StateCharts
- [PlayGo](http://www.weizmann.ac.il/mediawiki/playgo/index.php/Main_Page) (Weizmann Inst.)
- [Time Rover](http://www.time-rover.com/)
  
# Hybrid Systems
- [Ptolemy](http://ptolemy.eecs.berkeley.edu/index.htm) (BSD-3, Java): modeling, simulation, and design of concurrent, real-time, embedded systems (UC Berkeley)
- [HyTech](http://embedded.eecs.berkeley.edu/research/hytech/) (FUSC, C): computes condition under which a linear hybrid system satisfies a temporal requirement (UC Berkeley)
- [HyLink](http://hsver.crhc.illinois.edu/index.php/HyLink) (closed, MATLAB): Translates restricted class of Simulink/Stateflow models to hybrid automata (UIUC)
- [HARE](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HARE) (?): Abstraction refinement for safety
- [HTV](https://wiki.cites.illinois.edu/wiki/display/MitraResearch/HTV) (closed, MATLAB): verify systems from their simulation and run-time traces using imprecise samples and possibly incomplete models to compute overapproximations of bounded reach sets (UIUC)
- [START](http://www.andrew.cmu.edu/user/arieg/Rek/): time-bounded static analysis of concurrency properties of Real-Time Embedded Software
- [IF](http://www-verimag.imag.fr/~async/IF/index.html) (FUSC): static analysis, model-checking, test generation, [Open-Kronos](http://www-verimag.imag.fr/~tripakis/openkronos.html), [Kronos](http://www-verimag.imag.fr/DIST-TOOLS/TEMPO/kronos/): TCTL verification of Timed Automata (VERIMAG)
- [UPPAAL](http://www.uppaal.org/), [UPPAAL-Tiga](http://people.cs.aau.dk/ ̃adavid/tiga/) (FUSC): Timed automata (Uppsala Univ., Aaalborg Univ.)
	* [manipulate UPPAAL XML](https://launchpad.net/pyuppaal) (GPL-3, Python)
- [OPAAL](https://launchpad.net/opaal) (GPL-3, Python): distributed/parallel (discrete time) model checker for networks of timed automata  using MPI
- [ECDAR](http://people.cs.aau.dk/~adavid/ecdar/) (FUSC): timed interface theory (Aaalborg, INRIA, ITU)
- [SpaceEx](http://spaceex.imag.fr/) (GPL-3, C++): Reachability & safety verification (Verimag,  	Lab Jean Kuntzmann, DGA-MI)
- [PHAVer](http://www-verimag.imag.fr/~frehse/phaver_web/) (GPL-2, C++): verifying safety properies of hybrid systems (exact arithmetic, on-the-fly over-approximation of PWA dynamics, compositional & assume-guarantee reasoning) ([Verimag](https://sites.google.com/site/frehseg/))
- [ATAS](http://sourceforge.net/projects/atao/) (GPL-3, Python): Alternating 1-clock (fully decidable) Timed Automata Solver
- [CIF](http://se.wtb.tue.nl/sewiki/cif/start): Compositional Interchange Format for Hybrid Systems toolset
- [CheckMate](http://www.mathworks.com/matlabcentral/fx_files/15441/3/content/doc/main.htm) (MATLAB) modeling, simulation & investigation, [demos](http://www.mathworks.com/matlabcentral/fileexchange/17004-checkmate-demos)
- [PPL binding](https://launchpad.net/pyppl) (GPL-2, Python): for [Parma Polyhedral Lib](http://bugseng.com/products/ppl) features some specific methods for Timed Automata analysis
- [Passel](http://publish.illinois.edu/passel-tool/) (closed, C#/Python): invariant synthesis and inductive invariant proving (UIUC)
- [TEMPO](http://www.veromodo.com/) (FUSC): formal language for modeling distributed systems with (or without) timing constraints as collections of interacting state machines (UIUC)
- [Ariadne](http://trac.parades.rm.cnr.it/ariadne/) (GPL-3, C++/Python): dynamical systems set-based analysis (reachability analysis, robust simulation, safety verification - reset, flow, guard predicates given by nonlinear functions) (Univ. Udine, PARADES, CWI, Univ. Verona)

# Theorem Provers
- [PVS](http://pvs.csl.sri.com/) (GPL)
- [TPS](http://gtps.math.cmu.edu/tps.html): (CMU)
- [Coq](http://coq.inria.fr/) (INRIA, Ecole Polytechnique, Paris-Sud 11 Univ., Paris Diderot Univ., CNRS)
- [Isabelle](http://www.cl.cam.ac.uk/research/hvg/Isabelle/) (BSD): (Univ. Cabridge, TU Munchen, Univ. Paris-Sud)
- [HOL](http://www.cl.cam.ac.uk/research/hvg/HOL/): Iterative Theorem proving in higher-order logic (Univ. Cambridge)
- [HOL-omega](http://trustworthytools.com/id17.html)
- [ALF](http://www.cse.chalmers.se/research/group/logic/alf/guide.html) (Univ. Goterborg/Chalmers)
- [Alfa](http://www.cse.chalmers.se/~hallgren/Alfa/): successor of ALF
- [Agda](http://wiki.portal.chalmers.se/agda/pmwiki.php)
- [ACL2](http://www.cs.utexas.edu/users/moore/acl2/): part of Boyer-Moore family of provers (Univ. Texas at Austin)
- [INKA5](http://www.dfki.de/vse/systems/inka/inka5.html), [INKA](http://www.dfki.de/vse/systems/inka/): Inductive Theorem Prover
- [Otter & Mace2](http://www.cs.unm.edu/~mccune/otter/): first-order and equational logic
- [Prover9 & Mace4](http://www.cs.unm.edu/~mccune/prover9/): Successors of Otter & Mace2
- [EQP](http://www.cs.unm.edu/~mccune/eqp/): first-order equational logic: associative-commutative unification and matching, a variety of strategies for equational reasoning, and fast search
- [TWELF](http://twelf.org/wiki/Main_Page)
- [Maude ITP](http://maude.cs.uiuc.edu/tools/itp/): Inductive Theorem Prover
- [Mizar](http://mizar.org/)
- [PRL](http://www.nuprl.org/): (Cornell)
- [MetaPRL](http://www.cs.cornell.edu/jyh/metaprl/default.html)
- [Gandalf](http://deepthought.ttu.ee/it/gandalf/)
- [E-SETHEO](http://www4.informatik.tu-muenchen.de/~schulz/WORK/e-setheo.html): strategy-parallel compositional theorem prover for first-order logic with equality
- [SPASS](http://www.spass-prover.org/): First-Order Logic with Equality (Max Planck Inst. Inf.)
- [Omega](https://code.google.com/p/omega/) (BSD-3): cross between a purely functional programming language and a theorem prover
- [wikipedia list](https://en.wikipedia.org/wiki/Automated_theorem_proving)
- [this thread](http://cs.stackexchange.com/questions/868/types-of-automated-theorem-provers)

# Runtime Verification
- [MOP](http://fsl.cs.illinois.edu/index.php/MOP) (Java): Monitoring-Oriented Programming ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
- [CHIMP](http://www.cs.rice.edu/CS/Verification/Software/software.html): LTL -> monitors: nondeterministic finite-word automata that accept all illegal executions (Rice Univ.)
- [LTL_3](http://ltl3tools.sourceforge.net/) (GPL): LTL -> Moore FSM monitor
- [TOPL](http://rgrig.github.io/topl/) (OCaml): monitor Java programs
- [Breach Toolbox](http://www.eecs.berkeley.edu/~donze/breach_page.html)(BSD-3, MATLAB/C++): Simulation, verification of temporal logic properties and dynamical systems (ODE | Simulink) reachability analysis (UC Berkeley)

# Yet un-categorized
- [Maude](http://maude.cs.uiuc.edu/overview.html) (UIUC)
	* [C-Reducer](http://sysma.lab.imtlucca.it/tools/c-reducer/): Automatic c-reduction of object based modules for the Maude system (IMT Lucca)
	* [MESSI](http://sysma.lab.imtlucca.it/tools/ensembles/): Design, validation and performance evaluation of self-assembly strategies with Maude (IMT Lucca)
	* [Circ](http://fsl.cs.illinois.edu/index.php/Circ):  automated behavioral prover based on the circularity principle for Maude ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
- [K](http://www.kframework.org/index.php/Main_Page): rewrite-based executable semantic framework (UIUC)
- [Matching Logic](http://www.matching-logic.org/index.php/Matching_Logic): regard a language through both operational and axiomatic lenses at the same time ([UIUC](http://fsl.cs.illinois.edu/index.php/Main_Page))
- [Separation logic & local reasoning](https://wiki.mpi-sws.org/star/ToolSupport): wiki & tools list [Max Planck Inst. for Soft. Sys.](http://www.mpi-sws.org/~viktor/)
- [QMRes](http://www.cs.rice.edu/CS/Verification/Software/software.html): Multi-resolution with ZDDs implementation
- [MTSA](http://sourceforge.net/projects/mtsa/) (Public): Modal Transition Analyser (Imperial College London, Univ. Buenos Aires)

# Other tool lists
- [Wikipedia](https://en.wikipedia.org/wiki/List_of_model_checking_tools)
- [Yahoda](http://anna.fi.muni.cz/yahoda/) [Masaryk Univ.]
- [wikia](http://formalmethods.wikia.com/wiki/VL)
- [UPenn Hybrid System Tools Repository](http://wiki.grasp.upenn.edu/hst/index.php?n=Main.HomePage)
- [VERIMAG Tools](http://www-verimag.imag.fr/Tools,12.html?lang=)
- [verification tools for industrial automation](http://www.chihhongcheng.info/tools)
- [Networked Control Systems Repository](http://filer.case.edu/org/ncs/)

# databases
- [Buchi Store](http://buchi.im.ntu.edu.tw/index.php/home/index/)
- [Promela Database](http://www.albertolluch.com/research/promelamodels): (IMT Lucca)
- [Spec Patterns](http://patterns.projects.cis.ksu.edu/): patterns commonly occuring in specs of concurrent/reactive systems (LTL, CTL, GIL, QRE, ACTL, RAFMC) (Univ. Massachusetts Amherst)

# (non-common) abbreviations
- FUSC: Free Under Specific Condition (wikipedia term)
- BA: Buchi Automaton
- GBA: Generalized BA
