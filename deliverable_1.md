% Deliverable M2.B.1 (M6)\setcounter{page}{2}
% Requirements of verification and validation techniques and of AI techniques for space.

# Introduction
This deliverable describes the activities carried out in the first phase of the project by FBK, GSSI, and TAS-I and Task 2.B of workpackage 2.

As planned, the initial activities were dedicated to the identification of the key requirements for the validation and verification techniques and tools for smart and autonomous systems. The partners focused also on the needs for the project's case study.

Besides a few remote discussions, a first list of requirements has been compiled in a physical meetings hosted at GSSI on January 31, 2023. This list was refined in a second meeting held at GSSI on March 13 and 14, 2023 thank to the liaison that Inverso (GSSI) had put in place with TAS-I and FBK. Finally, steps forward on the applications of the verification and validation techniques on the case studies where agreed in a meeting held on June 8, 2023 betwen GSSI and TAS-I.

The rest of this document describes the main outcomes of Task 2.B so far. We note that this preliminary phase is not concerned with AI techniques, which will be considered at a later stage.

# Requirements
Smart and autonomous systems (SASs) pose peculiar challenges for their rigorous validation and verification. The main requirements on verification and validation of SASs derive from their specific functional and non-functional properties as well as from the complexity of their architecture. Indeed, SASs are typically distributed systems (no shared-memory) where communicating components may internally use shared-memory concurrency. For instance, an autonomous vehicle may exchange messages with the environment and use shared-memory concurrency in the components interacting with the global positioning system.

For the reasons above, the consortium will adopt a strategy that integrates static and dynamic techniques as well as model-driven approaches and verification & validation at the software level. On the one hand, traditional approaches should be complemented by run-time verification (such as monitoring) since e.g., testing can hardly cover all the possible behaviour SASs can have when operating 'in the field'. On the other hand, static techniques (such as behavioural typing), recently advocated to support the rigorous development of collective adaptive systems [1-8], can be adapted to the validation and verification of SASs in order to specify and guarantee properties.

For the formalisation and verification of SASs, we will study the integration of techniques and tools based on the expertise available in the consortium; in particular we will consider

- traditional model-checking approaches
- bounded model-checking
- behavioural typing
- choreographic design and verification
- run-time monitoring
- testing and simulation
- model-based quality analysis
- quality-based software refactoring

These approaches will tackle the verification of traditional safety and liveness properties of concurrent and distributed systems such as deadlock- or lock-freedom, non-functional properties related to performance or failures, and finally domain-specific properties. In particular, we have identified relevant elements of software platform of TAS-I that will be used to assess the validation and verification methods developed. More precisely we will perform analysis of TAS-I's library Can Lib to guarantee compliance with standards adopted at TAS-I and analyse the failure model of TAS-I's FDIR component.

Tool interoperability requires the definition of common intermediate representations and languages; for this reason FBK and GSSI have started the integration of their tools (details in the next section). In order to be able to use third-party tools, the partners will strive for adopting standard formats when possible.

# Initial outputs
The research on Task 2.B so far has produced the following outputs:

- FBK:
  - Inverso and Griggio have designed a proof-of-concept verification flow combining CSeq (GSSI) and Kratos (FBK) to analyse Thales’s C multi-threaded code in order to detect violations of safety properties.
  - Griggio has extended the Kratos software model checker of FBK (http://kratos.fbk.eu) in order to:
	- Improve the support for pointers and pointer arithmetic;
    - Support special custom integer types of arbitrary bit-width;
	- Support some GCC extensions to C used by CSeq.
	- All the above was done as a preparatory step for the integration of Kratos with CSeq mentioned above.
  - Tonetta and Griggio have analyzed the documentation provided by Thales to determine suitable verification techniques to be applied to the proposed case study.
		  
- GSSI:
  - Bartolo Burlo' (a PhD student at GSSI), Tuosto, and co-authors have developed a testing approach for testing RESTFul APIs; a paper describing the methodology and the related tool is under review. The main contribution is the definition of a domain specific language (DSL) inspired by binary session types [9,10] for model-driven testing of RESTful applications. The DSL allows developers to specify scenarios of effective usage of the RESTful API so to generate concrete tests through a driver that, interpreting the testing scenario, steers the testing session according to the expected usage of the API. The approach is being implemented in a prototype which will be evaluated on testing software publicly available on software repositories.
  - Inverso has conducted a preliminary study of coding standards and related static analysis rules for critical software.
  - Inverso and Griggio have designed a proof-of-concept verification flow combining CSeq (GSSI) and Kratos (FBK) to analyse Thales's C multi-threaded code in order to detect violations of safety properties.
  - Inverso has co-authored a paper on the certification of the proximal gradient method under fixed-point arithmetic for box-constrained QP problems; to appear on Elsevier's Automatica.
  - Inverso and Tuosto have supervise (a PhD student at GSSI, E. Sales) for the application of a sequentialisation technique to precisely detect races in multi-threaded C programs; a paper describing the methodology and the related tool is under review. The approach instruments C-like code in order to establish if shared memory can possibly accessed by concurrent operation at least one of which is a write operation. The approach leverages C-Seq for the analysis. Preliminary results indicate that, at the cost of a slightly less efficient analysis, the method rules out false positives and negatives within the given bounds.
  - Trubiani and Tuosto have co-authored a paper presenting a model-based approach for the performance analysis of collective adaptive systems. The extended version of a conference paper published at ISoLA 2022 [2] will appear in International Journal on Software Tools for Technology Transfer (STTT). The approach is based on choreographic models to specify the expected communication behaviour of ensembles of devices coordinating through attribute-based communication. To assess performance of systems by deriving queueing networks from the choreographic models specifying the system. Applications and experiments have been conducted in a robotic scenario.
  - Trubiani has co-authored a paper proposing a modular Quality-of-Service analysis of software design models, published at CAiSE2023. 
  - Trubiani has co-authored a paper presenting an exploratory study that evaluates the impact of architectural smells on software performance, published at EASE2023.
  - Tuosto has co-authored a paper published at ECOOP 2023 [11] developing a behavioural typing discipline supporting local-first principles in the development of peer-to-peer system. A prototype tool [12] has been integrated in the Actyx industrial platform for supporting their software production processes.
  - Tuosto has co-authored a paper proposing a compositional approach for the development of communicating systems. The paper will appear on the Journal of Logical and Algebraic Methods in Programming. The main contribution is a comprehensive treatment of compositional mechanisms. The work considers both symmetric synchronous communications and asymmetric synchronous communications (where senders decide independently which message should be exchanged). The composition mechanism preserves different properties under different conditions depending on the considered type of synchronous communication. It is shown that preservation of lock freedom requires an additional condition on gateways for asymmetric communication. Such condition is also needed for preservation of deadlock freedom, lock freedom or strong lock freedom for symmetric communications. This is not needed, instead, for preservation of either deadlock freedom or strong lock freedom with asymmetric interactions.
  - Tuosto has co-authored a paper [13] introducing a theory of formal choreography languages for the specification of communicating systems. An extended version will appear on the Journal of Logical Methods in Computer Science.

- TAS-I:
  - Paolo Serri ha illustrato al consorzio  le principali caratteristiche delle libreria usate da TAS-I (in particolare Can Lib)
  - Paolo Serri ha coordinato le visite on-site di Omar Inverso propedeutiche all'individuazione delle caratteristiche del software sviluppato da TAS-I di interesse per il progetto.

# References

[1] R. De Nicola, S. Jähnichen, and M. Wirsing. Rigorous engineering of
collective adaptive systems. International Journal on Software Tools for
Technology Transfer, 22(4):389–397, 2020.

[2] O. Inverso, C. Trubiani, E. Tuosto. Abstractions for Collective Adaptive Systems. ISoLA 2020, pages 243-260, 2020

[3] R. Hennicker, M. Wirsing. A Dynamic Logic for Systems with Predicate-Based Communication. ISoLA 2020, pages 224-242

[4] M. H. Johari, S. N. A. Jawaddi, and A. Ismail. Survey on formation
verification for ensembling collective adaptive system. Advances in Data
Computing, Communication and Security, pages 219–228, 2022.

[5] H. A. López and K. Heussen. Choreographing cyber-physical distributed
control systems for the energy sector. In SAC, pages 437–443. ACM, 2017.

[6] M. Loreti and J. Hillston. Modelling and analysis of collective adaptive
systems with CARMA and its tools. In International School on Formal Meth-
ods for the Design of Computer, Communication and Software Systems,
pages 83–119. Springer, 2016

[7] A. Vandin and M. Tribastone. Quantitative abstractions for collective
adaptive systems. In International School on Formal Methods for the
Design of Computer, Communication and Software Systems, pages 202–
232. Springer, 2016.

[8] M. Viroli, G. Audrito, J. Beal, F. Damiani, and D. Pianini. Engineering
resilient collective adaptive systems by self-stabilisation. ACM Trans-
actions on Modeling and Computer Simulation (TOMACS), 28(2):1–28,
2018.

[9] H. Huttel et. al. Foundations of Session Types and Behavioural Contracts. ACM Comput. Surv., 49(1):3:1--3:36, 2016

[10] M. Dezani-Ciancaglini and U. de'Liguoro. Sessions and Session Types: An Overview. WS-FM 2009.

[11] R. Kuhn, H. C. Melgratti, E. Tuosto. Behavioural Types for Local-First Software. ECOOP 2023: 15:1-15:28

[12] R. Kuhn, H. C. Melgratti, E. Tuosto. Behavioural Types for Local-First Software (Artifact). Dagstuhl Artifacts Ser. 9(2): 14:1-14:5 (2023)

[13] F. Barbanera, I. Lanese, E. Tuosto. Formal Choreographic Languages. COORDINATION 2022: 121-139
