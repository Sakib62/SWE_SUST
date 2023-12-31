<h1 align="center">Software Verification and Validation</h1>

**Book :**
- Software Testing - Principles and Practices

[✅**Book Link**][book]

[book]: https://drive.google.com/drive/folders/1-q6vEVlQxWmtmu-LkqoTIe_Ceqc3I8Mq?usp=sharing

**Question :** [**Exam.md**](Exam.md)

<br><hr><br>

**Theory Syllabus**
- **Ch1 - Introduction to Software Testing**
- **Ch2 - Software Testing Terminology and Methodology**
- **Ch3 - Verification and Validation**
- **Ch4 - Dynamic Testing: Black-Box Testing Techniques**
- **Ch5 - Dynamic Testing: White-Box Testing Techniques**
- **Ch6 - Static Testing**
- **Ch7 - Validation Activities**

<br><hr><br>

<h2>✅Ch1 - Introduction to Software Testing</h2>

- Software Testing - Myths and Facts
- Goals of Software Testing
    - Immediate
    - Long-term
    - Post-implementation
- Destructive approach : `Testing is the process of executing a program with the intent of finding errors`
- Testing model -> Software Model, Bug Model, Testing Methodology
- Effective vs Exhaustive Testing

<br><h2>✅Ch2 - Software Testing Terminology and Methodology</h2>

- **Error -- Bug -- Failure**
- Test suite -> Collection of test cases
- Properties of test cases
- **Life cycle of a bug**
    - Bugs-in phase : Requirement, Design, Coding
    - Bugs-out phase : Bug classification, isolation, resolution
- States of bug (*new, open, assign, rejected, deferred, test, reopened, verified, closed*)
- Classification of bug
    - Based on criticality : Critical, Major, Medium, Minor
    - Based on SDLC phase : Requirement, Design, Interface & Integration, System, Testing
- **⭐Software Testing Life Cycle (STLC)**
    - Test Planning, Design, Execution, Post-Execution/test review
    - Test execution level vs responsibility
        - Unit -> Developer
        - Integration -> Testers & Developers
        - System -> Testers, Developers, End-users
        - Acceptance -> Testers, End-users
    - Regression Testing -> To ensure that new code changes do not negatively impact the existing functionality of the application
- V-Testing model
- Testing Technique
    - Static
    - Dynamic (Black Box & White Box)

<br><h2>✅Ch3 - Verification and Validation</h2>

- Verification vs Validation
- **Verification - Are we building the right product?**
- **Validation - Are we building the product right?**
- V-Diagram and V-Testing
- V & V diagram
- V-diagram supports the concept of early testing. 
- V-diagram supports parallelism in the activities of developers and testers.

<br><h2>✅Ch4 - Dynamic Testing: Black-Box Testing Techniques</h2>

- Black Box Testing checks whether output is as expected
- White Box Testing checks if inefficient path/flow exists

**Black Box**
- ignores the structural/logical details of the software
- considers only the functional requirements
- also called `functional testing`
- various methods to test a software product using black-box techniques
- The objective of any test case is to have maximum coverage and capability to discover more and more errors.
- **⭐Boundary Value Analysis (BVA)**
    - Boundary Value Checking (BVC) : 
        - `4n + 1` test cases for n input variables
        - Min, Min+, Max, Max-, Nom(nominal)
        - *Inside testing boundary*
    - Robustness Testing: 
        - `6n + 1` test cases for n input variables
        - Min, Min+, Min-, Max, Max-, Max+, Nom
        - *Out of boundary*
    - Worst Case Testing : 
        - `5^n` test cases for n input variables
- **⭐Equivalence Class Testing**
- **⭐Decision Table-Based Testing**

<br><h2>✅Ch5 - Dynamic Testing: White-Box Testing Techniques</h2>

- `glass-box/structural/development testing`
- entire design, structure, and code have to be studied for this type of testing
- intention is to test the logic to achieve required functionalities & to ensure internal parts of the software are adequately tested
- **Need of White-box Testing**
    - testing the module for initial stage testing
    - logical path
    - typographical errors
- **Logic Coverage Criteria**
    - test cases are designed to cover every element of the logic
    - **Statement Coverage** - test case so that every statement of the module is executed once. Necessary but not sufficient for logic coverage.
    - **Decision or Branch Coverage** - each branch direction must be traversed at least once.
    - **Condition Coverage** - each condition in a decision takes on all possible outcomes at least once.
    - **Decision/Condition Coverage** - each decision & each condition in a decision takes on all possible outcomes at least once and each point of entry is invoked at least once.
    - **Multiple Condition Coverage** - sufficient test cases such that all possible combinations of condition outcomes in each decision and all points of entry are invoked at least once.
- **Basis Path Testing**
    - oldest structural design technique
    - selecting the paths that provide a basis set of execution paths through the program
    - based on control structure, a flow graph is prepared and all possible paths can be covered and executed during testing
    - control flow graph is a graphical representation of control structure of a program. Notations that are used : Node, Edge/link, Decision Node, Junction Node, Region
    - **flow graph is also known as decision-to-decision-graph or DD graph**
    - path testing terminology : path, segment, path segment, length, independent path
    - **Cyclomatic Complexity = number of independent paths**<br>Formula to calculate it :
        - V(g) = e - n + 2p ; *e is number of edges, n is number of nodes, p is number of components*
        - V(g) = d + p; *d is the number of decision nodes*
        - V(g) = number of regions in the graph
    - switch case and multiple if-else have more than two arrows leaving a decision node.<br>d = k - 1; *k is the number of arrows leaving the node*
    - If a program has multiple components X, Y, Z;  V(G) = V(x) + V(y) + V(Z)<br>Or, count the number of nodes and edges in all components of the program collectively and apply V(g) = e - n + 2p
    - Draw DD graph -> Calculate CC -> List all independent paths -> Design test cases from independent paths
- **Graph Matrices**
    - path tracing with flow graph may be time consuming
    - manual path tracing becomes difficult as the size of graph increases
    - **Graph Matrix - a tool for automation of path tracing**
    - A graph matrix is a square matrix whose rows and columns are equal to the number of nodes in the flow graph
    - Each row and column identifies a particular node and matrix entries represent a connection between the nodes.<br>Conventionally, digits are used for nodes and letter symbols for edges
    - **Connection Matrix** - The links between two nodes are assigned a link weight which becomes the entry in the cell of matrix.<br>When the connection exists, the link weight is 1.
    - **Connection Matrix is used to find the Cyclomatic Complexity**<br>For each row, count number of 1s. Subtract 1 from the number (ignore blank rows).<br>Add the final count of each row.<br>Add 1 to the final sum. It is the Cyclomatic number of the graph.
    - Graph matrix is used to find the set of all paths between all nodes.<br>The power operation on matrix expresses the relation between each pair of nodes via intermediate nodes.<br>**m'th power of the matrix represents path segments that are m-links long.**
- **Loop Testing**
    - extension to branch coverage
    - Four different kinds of loops : Simple, Nested, Concatenated, Unstructured
- Data Flow Testing
- Mutation Testing

<br><h2>✅Ch6 - Static Testing</h2>

- Inspection Process
    - Gilb Inspection
    - Humphrey's Inspection process
    - N-Fold Inspections
- Structured Walkthrough
- Technical Review

<br><h2>✅Ch7 - Validation Activities</h2>

- Unit Validation Testing
- Integration Testing
    - Decomposition-Based Integration
        - Non-Incremental
        - Incremental
            - Top-down : stub needed. Depth first, Breadth first
            - Bottom-up : driver needed
            - Sandwich
    - Call Graph-Based Integration
    - Path-Based Integration : MEP Graph, MM Path
- System Testing : Recovery, Security, Performance, Load, Stress, Usability, Compatibility/Conversion/Configuration
- Acceptance Testing : Alpha, Beta