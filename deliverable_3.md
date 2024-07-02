% Deliverable M2.B.3 (M18)\setcounter{page}{2}
% Validation & Verification techniques for smart systems
% and prototype of AI software for space


# Introduction
This deliverable describes the activities carried out in the first half of the second year of the project by FBK, GSSI, and TAS-I and Task 2.B of workpackage 2.

The planned activities were to define initial versions of validation & verification techniques for smart and autonomous system. It was also planned to consider specialization of such techniques to AI techniques for space with a first prototype.

# Activities
Two set of activities were carried out. The first set some of the partners (mainly FBK and GSSI) worked on the definition of general verification and validation techniques, to the development of the corresponding prototypes, as well as the investigation of their integration. A second set of activities (mainly involving GSSI and TAS-I) was dedicated to the exploration of techniques specific to AI software for space.

## General techniques
The approaches studies for the verification and validation of systems can be broadly divided in model-driven or software-based.

The following methods can be ascribed to the first category since they are based on behavioural specification:

- The work on swarm computing initiated at GSSI [1,2] has further been developed within a collaboration involving the SME Actyx (Germany) and DTU (Denmark); in the context of the TARDIS EU project involving Actyx and DTU, the team is developing a compositional framework for swarm computation based on the work carried out in [1,2]. The approach currently explored is to specify composition mechanisms of swarm protocols that preserve eventual consistency of systems using a generalisation of the conditions found [1].

- The work on model-driven testing RESTful APIs described in Deliverable M2.B.1 has been published in [3]. Besides the prototype implementation the paper provides an extensive validation of the approach by considering publicly available application taken from software repositories. The paper also shows the advantages of the approaches on state-of-the-art competitors.

- A new orchestration model has been designed in [4] together with a prototype implementation (awarded the best artefact price). The model is inspired by smart contracts and has been validated on the Microsoft Azure repository of smart contracts. The study has highlighted some weakness of the model in the handling of roles and the team is now working to generalise the approach to overtake this limitation.

- A bounded model-checking algorithm for Quality of Service properties of distributed communicating components based on a dynamic temporal logic indexed by choreographic specifications has been published in [5] (best paper award). A related tool paper has been accepted at FM 2024.

The following methods can be ascribed to the software-base category:

- GSSI refined the initial prototype for data race detection in multi-threaded C programs. The tool has been validated on benchmarks found in the literature. The team has also designed a more specific set of benchmarks. These results, which will appear at FM 2024 confirm that the approach covers cases that competing tools cannot handle and that the method rules out false positives and negatives within the given bounds.

- In collaboration with DTU (Denmark), KTH (Sweden), and UBA (Argentina), GSSI has tackled the problem of embedding _join patterns_ [6] in an actor-based programming language. The team has considered, in particular, how to specify a suitable notion of message matching, how to implement it correctly and efficiently, and how to systematically evaluate the implementation performance. The initial results are (i) a formalisation of a notion of _fair and deterministic join pattern matching_, (ii) a stateful, tree-based  algorithm to find such matches, and (iii) a Scala library allowing programmers to use the fair deterministic join pattern matching in concurrent and distributed Scala programs.

- An infrastructure for dynamic semantic-based search and binding of distributed communicating components has been published in [7]. The infrastructure use a notion of compliance based on bisumulation and support multilanguage programming allowing to compose components developed in Python, Java, and Go.

- GSSI, in collaboration with the Politecnico of Milano, has contributed to a modular approach to analyse the quality of service of different software design models, thus bridging the gap between multiple model abstractions, see [11].

- GSSI, in collaboration with the University of Auckland, has contributed to the model-based verification of adversarial conditions by means of design patterns that support the control and reconfiguration of software tasks, see [12].



## Techniques for AI software for space

- FBK continued the research and development of VIVAS, a framework for the simulation-based Verification and Validation (V&V) of autonomous systems with AI components using a methodology based on a combination of Model Checking, coverage-based testing, simulation, and runtime monitoring [8]. The framework has been originally applied to the analysis of an autonomous rover for planetary exploration, based on an accurate simulator for space applications [8], and then subsequently generalised to the automotive domain, for the validation of agents for autonomous driving [9]. Finally, the framework has been recently extended with a contract-based methodology in order to better identify the causes for system failures [10].

- GSSI has contributed to the development of a discrete-event simulator to analyse multiple coordination mechanisms among agents, thus optimising the scheduling of software tasks, see [13]. 

- GSSI, in collaboration with University of Milano-Bicocca, has contributed to the development of a framework for detecting software antipatterns in java programs, thus supporting the early detection of performance issues, see [14].

- GSSI, in collaboration with Politecnico of Milano and IMT Lucca, has contributed to the development of autoscaling solutions to efficiently manage system requests, thus improving the energy consumption of cloud resources, see [15].



# References
[1] R. Kuhn, H. C. Melgratti, E. Tuosto. Behavioural Types for Local-First Software. ECOOP 2023: 15:1-15:28

[2] R. Kuhn, H. C. Melgratti, E. Tuosto. Behavioural Types for Local-First Software (Artifact). Dagstuhl Artifacts Ser. 9(2): 14:1-14:5 (2023)

[3] C. Bartolo Burlò, A. Francalanza, A. Scalas, E. Tuosto. COTS: Connected OpenAPI Test Synthesis for RESTful Applications. COORDINATION 2024: 75-92

[4] J. Afonso, E. Konjoh Selabi, M. Murgia, A. Ravara, E. Tuosto. TRAC: A Tool for Data-Aware Coordination - (with an Application to Smart Contracts). COORDINATION 2024: 239-257

[5] C. G. López Pombo, A. E. Martinez Suñé, E. Tuosto. A Dynamic Temporal Logic for Quality of Service in Choreographic Models. ICTAC 2023: 119-138

[6] C. Fournet and G. Gonthier. The Reflexive CHAM and the Join-Calculus. PoPL 1996

[7] C. G. López Pombo, P. Montepagano, E. Tuosto. SEArch: An Execution Infrastructure for Service-Based Software Systems. COORDINATION 2024: 314-330

[8] S. Fratini, P. Fleith, N. Policella, A. Griggio, S. Tonetta, S. Goyal, T. T. H. Le, J. Kimblad, C. Tian, K. Kapellos, C. Tranoris, Q. Wijnands. Verification and Validation of Autonomous Systems. ASTRA 2023.

[9] S. Goyal, A. Griggio, S. Tonetta. System-level Simulation-based Verification of Autonomous Driving Systems with the VIVAS Framework and CARLA Simulator. Submitted to the special issue "Advances in Formal Methods for Autonomous Systems" of Science of Computer Programming, 2024.

[10] S. Goyal, A. Griggio, S. Tonetta. Leveraging Contracts for Failure Monitoring and Identification in Automated Driving Systems. Under review, 2024.


[11] Riccardo Pinciroli, Raffaela Mirandola, Catia Trubiani: Modular Quality-of-Service Analysis of Software Design Models for Cyber-Physical Systems. International Conference on Advanced Information Systems Engineering (CAiSE), 88-104, 2023. 


[12] Kenneth Johnson, Samaneh Madanian, Catia Trubiani "Patterns of Applied Control for Public Health Measures on Transportation Services under Epidemic", in International Conference on Software Engineering for Adaptive and Self-Managing Systems (SEAMS), 150-160, 2024.

[13] Riccardo Pinciroli, Catia Trubiani: Performance Analysis of Fault-Tolerant Multiagent Coordination Mechanisms. IEEE Trans. Ind. Informatics 19(9): 9821-9832 (2023).

[14] Catia Trubiani, Riccardo Pinciroli, Andrea Biaggi, Francesca Arcelli Fontana: Automated Detection of Software Performance Antipatterns in Java-Based Applications. IEEE Trans. Software Eng. 49(4): 2873-2891 (2023).

[15] Giovanni Quattrocchi, Emilio Incerto, Riccardo Pinciroli, Catia Trubiani, Luciano Baresi: Autoscaling Solutions for Cloud Applications Under Dynamic Workloads. IEEE Trans. Serv. Comput. 17(3): 804-820 (2024).
