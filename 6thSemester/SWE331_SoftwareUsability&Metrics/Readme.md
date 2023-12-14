<h1 align="center">Software Usability and Metrics</h1>

**Book :**
- Software Measurement and Estimation : A Practical Approach by Linda M. Laird & M. Carol Brennan

[✅**Book Link**][book]

[book]: https://drive.google.com/drive/folders/1Xfwx80e59zGNAfrznqzT6ev_If1cBrSD?usp=sharing

**Question :** [**Exam.md**](Exam.md)

**🔥Syllabus : Chapter 1 to 7**

-   |[**Chapter 1**][1] | [Chapter 2][2] | [Chapter 3][3] | [Chapter 4][4]|
    |--------- | --------- | --------- | ---------|
    |[**Chapter 5**](#ch5) | [**Chapter 6**][6] | [**Chapter 7**][7] |       |

[1]: #ch1
[2]: #ch2
[3]: #ch3
[4]: #ch4
[6]: #ch6
[7]: #ch7

<br><hr><br>
<details>
<summary><h2 id="ch1">✅Chapter-01: Introduction</h2></summary>

**🔥Why measurement?**
- 23% canceled before completion
- 28% of completed projects on time, budget, features
- 45% overrun budget

**🔥Skills needed for prediction and estimation**
- Software development related risk
- Activity control / predict
- Managing the risks
- Delivery Reliability

**🔥Maturity of an organization**
- **CMMI (Capability Maturity Model Integration)**
- 5 levels
- **i) Initial ii) Managed iii) Defined**
- **iv) Quantitatively Managed v) Optimizing**
- Process Area (PA) for each levels
- For ii) Managed: Project plan, Project montioring & control
- For iv) Quantitatively Managed: Establishing quantitative view
- For v) Optimizing: Continuous measurable improvement

</details>

<br><hr><br>
<details>
<summary><h2 id="ch2">✅Chapter-02: What to Measure</h2></summary>

**🔥3 information before creating measurement model**
- Customer of the metric
- What are the goals
- What metrics, when collected

How to make such model?

**🔥GQM (Goal Question Metric) approach**
- Identify goal
- Question(s) identification
- Define the metric

**🔥Decision Maker Model**
- Client is the decision maker
- Decision changes over time 
    ```mermaid
        graph LR
        A[Project Decisions] -->|Information| B[Project Measures]
        A -->|Data/Product| B
    ```
**🔥Standard Driven Metrics**
- Software Engineering Institute (SEI)
- Minimal set consists of following:
- System size
- Project duration
- Effort
- Defects
- Productivity

**🔥GQMM (Goal Question Metric Mechanism)**
- who will collect and report data
- how frequently data will be collected and reported
- Without mechanism, data may get corrupted & budget overrun

**🔥What to measure is a function of time**
- characteristics of any metrics program
- what to measure varies based on current position in lifecycle
- business needs change, metrics must change too
- metrics can lose their efficacy over time

</details>

<br><hr><br>
<details>
<summary><h2 id="ch3">✅Chapter-03: Measurement Fundamentals</h2></summary>

Number of lines of code (LOC) may vary depending on the rule.<br>
LLOC = logical lines of code<br>

**🔥Measurement models**
- Making the unmeasurable measurable.
- **3 types of model : text, diagrammatic, algorithmic**
- Text model - Items clearly defined but their relationships difficult to visualize
- Diagrammatic model
    ```mermaid
        flowchart LR;
        1([Features]) 
        2([Size])
        3([Effort])
        4([Cost])
        5([Schedule])
        6([Defects])
        7([Resources])
        1--->2--->3--->4
        3--->5--->6
        2--->6
        7--->5
    ```
- Algorithmic / parametric model
- Effort = Schedule * Resource
- 3 types of model example with -> "Response Time"

**🔥How to measure anything?**
- Pantometric paradigm
- reduce to 'minimum required', visualize, divide, measure

**🔥Meta Model for metrics**
- Abstract : Concept & Definition
- Empirical World : Operational Definition & Measurement in real world
    ```mermaid
        flowchart LR;
        root1(Concept)
        1(Definition)
        2(Operational Definition)
        3(Measurement in real world)
        root1-->1-->2-->3
    ```

**🔥5 types of measurement scale**
- **Nominal :** Orderless list, no relationship. Central tendency - only mode
- **Ordinal :** Ordered set, priority. Mode and Median. Cannot say 2 Major bug > 4 minor bug
- **Interval :** Consistent Difference. Addition, subtraction. Mode, Median, Mean
- **Ratio :** (+, -, *, /). Mode, Median, Mean
- **Absolute :** Number of occurrence. Mode, Median, Mean. No negative value

**🔥Measures of variability**
- **Range :** High point - Low point
- **Deviation :** Distance from mean

```math
\begin{flalign}
\textrm{Variance for population: } \sum_{}^{} \frac{\textrm{Deviations}^{2}}{N} \\
\textrm{Variance for sample: } \sum_{}^{} \frac{\textrm{Deviations}^{2}}{N-1} \\
\textrm{Standard Deviation (SD): }\sqrt{\textrm{Variance}} \\
\textrm{Index of Variation (IV): } \frac{\textrm{SD}}{Mean} 
\end{flalign} 
```

<!-- - **Variance :** 
    - For population $\small\sum(\text{deviations}^2) / N$
    - For sample $\small\sum(\text{deviations}^2) / (N - 1)$
- **Standard Deviation (SD) :** $\sqrt{\text{variance}}$
- **Index of Variation (IV) :** $\large\frac{\text{SD}}{\text{mean}}$ -->

- Validity & Reliability of measurement
- Measurement error - Systematic & Random 

</details>

<br><hr><br>
<details>
<summary><h2 id="ch4">✅Chapter-04: Measuring the Size of Software</h2></summary>

Size is one of the most basic attributes of software.<br>
Measuring size in both **physical and functional sense**.

🔥**Physical measurements**
<br>

- **⭐Size**
    - **Lines of Code (LOC)** is the traditional measure for software size
    - does not adequately address functionality, complexity and technology
    - issue is which rules to follow
    - **KLOC** -> 1000 LOC, **NKLOC** -> non-commented thousand LOC, **LLOC** -> Logical LOC
    - Software Engineering Institute (**SEI**) -> framework for counting source code
    
    <br>
- **⭐Language Productivity Factor**
    - **"Gearing Factor"** compares the expressiveness & differences in productivity of languages
    - The more productive a language is, the fewer LOC need to be written
    - show the **relationship between LOC and function points**
    - C++ 55, Java 53, C 128
    - how many LOC need to be written to implement a function point
    - compare projects normalized by functionality rather than lines of code
    
    <br>
- **⭐Counting reused and refactored code**
    - NASA's classification scheme with an ordinal scale of 4 points
    - reused verbatim, slightly modified (< 25%)
    - extensively modified (>= 25%), new
    - simplified to reused (< 25%) and new
    
    <br>
- **⭐Length of specification and design**
    - Number of pages & Number of "shalls"
    - specification-to-code & design-to-code expansion ratio
    - for design-to-code expansion ratio of 300, project with 12 pages of design, need to write 3600 NLOC
    - CMMI level 3 or higher org. use **"shalls" for mandatory requirements**
    - These requirements can be traced to design, code, test cases
    ```
    If avg. number of staff months per "shall" is 1.05 with a standard deviation of 10%, 
    estimated no. of staff months for project with 100 "shall" would be 
    
    100 * 1.05 = 105 +- 21 staff months with 2 SD of 20%
    (using 2 SD for increase in accuracy)

    The interval contained within 1 SD of the mean is ~68% of the population, 2 Sd is ~95%, 3 Sd is 99.73%
    ```
    ```
    The standard deviation is a measure of how much the data is spread out from the mean. A high SD means that values are generally far from the mean.

    The empirical rule, also known as the 68-95-99.7 rule, is a statistical rule of thumb that states that for a normal distribution, approximately:
    
    68% of the data falls within one SD of the mean. 95% within two. 99.7% within three.

    For example, if the mean height of a population is 5 feet 6 inches, and the SD is 2 inches, then:
    
    Approximately 68% of the population will have a height between 5'4'' inches and 5'8''. 95% between 5'2'' and 5'10'' //for 3sd , range too large? usefulness?
    ```

<br>

🔥**Measuring Functionality**

Physical measurements - less about problem being solved, more about development technology.
<br>
Need to measure the size - based on what system needs to do rather than how it does it internally

**Function Point (FP) approach** -> count the inputs, outputs, interfaces, databases & inquiries in a system

- **⭐Function Point Analysis (FPA)**
    - indirect measure for the functional size of a system
    - most widely used **Functional Size Measurement (FSM)**. Others are : Lorenz-Kidd Method, Object Points, WebMO & Use Case Points.
    - estimating the size of the system from its external transactions & databases
    - counting FP in **IFPUG (International Function Point User Group)** version of Function Point Analysis

<br>

- **⭐Calculating Function Points**
    - system's functionality decomposed into components of
        - inputs, outputs, external interface files (maintained by another system)
        - internal data files (maintained by this system)
        - inquiries
    - each component's difficulty is rated as **simple, average, or complex**
    - complexity rating is given to each component based on its type & difficulty
    - complexity rating represent the relative implementation effort
    - **UFP (Unadjusted Function Point)** = sum of all of the complexity ratings
    - **VAF (Value Adjustment Factor)** = based on the complexity of the overall system
    - **AFP (Adjusted Function Point)** = multiplying VAF by the UFPs
    - IFPUG rules to determine component difficulty & to count GUIs
    - getting-started strategy of rating everything as average complexity
    - **Additional adjustment** is made based on the expected **implementation difficulty** of the system.
    - Calculating **VAF** based on **14 General System Characteristics (GSC)** rated from **0 (no influence) to 5 (extensive influence)**
    - `AFPs = UFPs * (0.65 + 0.01 * VAF)`
        ```
        For an "average" system, with all average values of 2.5 for the 14 GSCs, the VAF = 14*2.5 = 35

        AFP = UFP * (0.65+0.35) = UFP, that is AFP equals 100% of the UFP
        ```
    - The VAF can adjust the function point count by +- 35% (if all of the GSCs are 5 or all are 0)
    - **Software Productivity Research (SPR)** proposed another method for **VAF**
        - This method uses **Problem Complexity** & **Code Complexity** to adjust the function point count
        - They are rated on a scale of **1 (simple algo/data) to 5 (very complex algo/data)**
        - `VAF = 0.4 + 0.1 * (Program Complexity + Data Complexity)`
        - 
            ```
            AFP = UFP * (0.4 + 0.1 * (PC + DC))
            If both factors are average (3), VAF = 0.4+0.1*(3+3) = 0.4+0.6 = 1

            Adjustment Range is +- 40% (if both factors are very complex or simple)
            It is +- 35% in the IFPUG method
            ```
    - 
        ```
        Estimate the effort to build the system. Assume a productivity of 10 FPs per staff month, with a standard deviation of +-1 staff month.

        Calculate AFP.

        If it is 34.3, then estimated number of staff months = 34.3/10 = 3.4
        Since the sd is +- 1 staff month, 1 sd is 34.3/9 = 3.81 and 34.3/11 = 3.12
        Therefore, estimated effort is between ~3.1 and ~3.8 staff months ~68% of the time.

        To reduce expected staff months, reduce the number of AFPS : 
        i) Reduce UFPs -> reduce functionality, might hurt project or -> simplify the design
        ii) Reduce VAF -> change some of the assumptions about GSCs

        Budget and staffing will always be inadequate. How to reduce the required effort?
        Simplify the solutions that reduces the proxy points, rather than working overtime or cutting features.
        ```

<br>

- **⭐Converting Function Points to Physical Size**
    - The primary purpose of the gearing factors is to convert FP to LOC, based on implementation language
    - The issue is which gearing factor to pick. Avg, max, min, median. David Consulting Group (DSG), Jones number, QSM.
    - Start with avg.

<br>

- **⭐Other FP Engineering Rules**
    - Schedule = FP^0.4, in calender months
        - the power factor ranges from ~0.32 to ~0.45
        - 0.4 is the average for 1000 FP projects
    - staff = FP / 150
    - Effort = Staff * Schedule
        ```
        Estimate the effort for a system with 25.93 FPs, using the Jones engineering rules for function points.

        Round the number of FP to 26. Power factor 0.32 for smaller projects
        Schedule = 26^0.32 = 2.84 calender months
        Staff = 26 / 150 = 0.173!!
        Effort = 0.173 * 2.84 = 0.5 staff month
        
        Schedule seems a reasonable number, but staffing is not & does not match well with the LOC engineering rules.

        Staffing rule does not hold up well for very small projects.
        Accuracy is low, but these rules give a starting point.
        ```
<br>

- **⭐Feature Points**
    - simple extension of FP for scientific applications.
    - originally designed for use with Management Information System (MIS)
    - developed by SPR to give additional weight to algorithmic complexity
    - shows an evolution of FPs to better match another problem domain space

</details>

<br><hr><br>
<details>
<summary><h2 id="ch5">✅Chapter-05: Measuring Complexity</h2></summary>

The more complex the code, the more difficult it is to understand, debug and maintain. This in turn implies more defects and lower productivity.

**Complexity - Structural, Conceptual, Computational**  

The complexity metrics are operational definitions of good design and good programming and are indicators for productivity and defect proneness. 

**🔥Structural Complexity**
- looks at design and structure of the software
- simplicity in design -> modularity, loose coupling, tight cohesion
- simplicity in structure -> simple control flow & interfaces
- predict defect proneness, productivity, and maintainability

- **⭐Size : System & Module size**
    - Typically measures LOC or function points
    - As a system increases in size, the relationship between defect and size is relatively linear. Defect density is relatively constant.
    - For modules size, there is a **sweet spot between 200 - 750** LOC per module.<br>A module is defined as a set of executable code that has one entrance and one exit.<br>At the start, density of defect is high. It decreases to a point then increase again due to less maintainability.
- **⭐Cyclomatic Complexity**
    - Measures the control flow within a module
    - Cyclomatic number of a graph denoted by `V(g)`
    - Calculated by counting the number of **linearly independent paths** within a program to determine the minimum number of unique tests to execute every executable statement.
    - `V(g) = e - n + 2`; g is the control graph of the module, e is the number of edges, n is the number of nodes.
    - `V(g) = bd + 1`; bd is the number of binary decisions in the control graph.<br>If there is a n-way decision, it is counted as n-1 binary decisions.
    - High CC numbers imply a high complexity and difficulty in maintaining & testing. **CC > 20 cause for concern and CC > 50 cause for alarm.**
    - **Side effects of CC** -> Bad Fix Probability : inserting a defect while trying to fix another defect.
    - **Usefulness of CC** -> Identify overly complex and non-complex parts. Estimate maintenance and testing effort.
    - **Extensions to CC** 
        - Cyclomatic Complexity Density (**CCD**) = CC / LOC
        - Essential Cyclomatic Complexity (**ECC**) -> Measure of unstructuredness of code, such as gotos in the middle of while loops<br> **CC after removing all of the structured constructs (if, else, while, repeat, sequence)**
        - ECC of programs that contain only structured programming constructs is 1
- **⭐Halstead's Metrics**
    - Measures the number of "operators" and "operands" in the code
    - Operands are variables, constants, and strings. Operators are everything else.
    - Operators that are paired (such as while do or {}) only count as one.
        ```
        If n1 = number of distinct operators
        n2 = number of distinct operands
        N1 = total number of operators
        N2 = total number of operands,
        
        Then Length, N = N1 + N2
        Vocabulary, n = n1 + n2
        Volume, V = N(log2(n))
        Difficulty, D = (n1/2) * (N2/n2)
        Effort, E = D * v
        ```
    - Calculated after the code is written, hence no predictive power for development effort.
    - Used as a predictor of maintenance effort.
- **⭐Information Flow Metrics**
    - Measures the flow of data into and out of modules
    - Predicts fault-prone & complex module
    - Information Flow Complexity **(IFC) = (fanin * fanout)^2**
    - Weighted IFC = length * IFC
    - **Fanin = local flows into a procedure + number of data structures from which the procedure retrieves data**  
    - **Fanout = local flows from a procedure + number of data structures that the procedure updates**
    - Length = number of source statements in a procedure excluding comments.
    - **Fanout much better indicator than Fanin.**<br>Evolve Fanin to ignore the number of calls, only count the number of data structures read.
    - **High IFC of a procedure indicates** -> lack of cohesion,<br>potential choke point due to too much information traffic,<br>Excessive functional complexity<br>Need to redesign/simplify/extensive testing
- **⭐System Complexity**
    - Measures the complexity of the entire system in terms of maintainability and/or overall design
    - **💥Maintainability Index**
        - to indicate modules & software that are difficult to maintain as well as to develop initially
        - **composite metric based on LOC, Halstead's metrics & cyclomatic complexity**
        - `MI = 171 - 5.2ln(aV) - 0.23aV(g') - 16.2ln(aLOC) + 50sin[(2.4 * perCM)^0.5]`
            ```
            aV = average Halstead volume V per module
            aV(g') = average extended cyclomatic complexity per module
            aLOC = average count of Lines of Code per module
            perCM = average percent of lines of comments per module (optional)
            ```
        - The coefficients were empirically derived from actual usage data
        - **MI > 85 = Highly maintainable, MI > 65 && <= 85 = Moderately maintainable, MI <= 65 = Difficult to maintain**
        - MI uses the average per module. **Start off with a score of 171**. All factor impact MI negatively except perCM. The higher the volume, ECC, LOC, the lower the MI.
        - Consistent with experts in assessing which modules and systems are more or less maintainable and give potential targets for redesign
        - Tools exist to automatically calculate MI
    - **💥Agresti-Card-Glass System Complexity Metric**
        - based on the structured design modularity principles of coupling and cohesion
        - **Total system complexity = Total structural (intermodule) complexity + Total data model (intramodule) complexity**
        - designed for large systems using top-down design methodologies and reinforces top-down design techniques
- **⭐Object-Oriented Design Metrics**
    - Functional designs are structured around procedures and modules and decomposition of those
    - **Object Orient designs are structured around objects** which encapsulates state, characteristics and possible set of actions for that object
    - LOC is a measure of size for procedural code, but does not make much sense for OO code. Fanout may not make much sense either.
    - Need metrics to **measure classes, modularity, encapsulation, inheritance, and abstraction**
    - The **CK metrics suite** is a popular set of OOD metrics that consists of **six metrics** : 
        - WMC - Weighted Methods per Class
        - DIT - Depth of Inheritance Tree
        - NOC - Number of Children
        - CBO - Coupling Between Object Classes
        - RFC - Response For Class
        - LCOM - Lack of Cohesion on Methods

**🔥Conceptual**
- refers to difficulty in understanding
- tends to be more psychological, base on mental capacity and thought processes of programmers
- difficult to quantify
    - how difficult to specify a solution
    - amount of time required to understand the code itself
- comparing design & implementation


**🔥Computational**
- complexity of the computation begin performed
- measure by required **amount of time**(no. of instructions) & **space**(disk, memory)
- **evaluate & compare implementations and design** for efficiency
- to ensure that complexity of solution does not exceed the inherent complexity of the problem being solved

</details>

<br><hr><br>
<details>
<summary><h2 id="ch6">✅Chapter-06: Estimating Effort</h2></summary>

**🔥Cone of Uncertainty**
- Barry Boehm published the classical chart which became known as "cone of uncertainty"
- **Represents the estimated accuracy of estimates at different phases of a project**, the accuracy of an estimate is a factor of +- 4
- If a project is estimated to need 200 staff months, it could take anywhere between 50 and 800 staff months
- **Estimate accuracy increases along the life cycle of a project**
- Phases -> Feasibility, Plans and Requirements, Product Design, Detailed Design, Development and Test
- **Instead of giving "the number", we need to give ranges and views based on probabilistic distributions.**
- The "pX view" means that there is an X% probability of not exceeding the estimate
    <table>
        <caption>
            <b>Estimation Uncertainty Engineering Rules</b>
        </caption>
        <tr>
            <td align="center"><b>Project Phase</b></td>
            <td align="center"><b>Feasibility</b></td>
            <td align="center"><b>Requirements</b></td>
            <td align="center"><b>Design</b></td>
            <td align="center"><b>Coding</b></td>
            <td align="center"><b>Testing</b></td>
        </tr>
        <tr>
            <td align="center"><b>%Uncertainty</b></td>
            <td align="center">+100/-50</td>
            <td align="center">+50/-25</td>
            <td align="center">+20/-10</td>
            <td align="center">+10/-5</td>
            <td align="center">+5</td>
        </tr>
    </table>
- If current p50 estimate is 50 staff months and currently in design phase, using engineering rules, expected range is between 45 and 60 staff months
</details>

<br><hr><br>
<details>
<summary><h2 id="ch7">✅Chapter-07: In Praise of Defects: Defects and Defect Metrics</h2></summary>

Defects/Bug/Fault are real, observable manifestations and indications of the software development progress, process, and quality.

**🔥Fault vs Failure**
- Faults are defects that are in the system at some point in time.
- Failures are faults that occur in operation.
- Defects metrics measure faults.
- Reliability metrics measure failures.

<br>

**🔥Software Availability**
- If code contains faults but they are never executed in operation, then the system never fails.<br> The **mean-time-between-failures (MTBF)** for the system will approach infinity and software availability will be 100%.
- If there is only one fault and it is executed in the boot sequence, the system will fail every time.<br>**MTBF** approaches 0 and software availability will be 0%.

<br>

**🔥Defect Dynamics and Behavior**
- **Defect Arrival Rates** -> follow Rayleigh curve. bell shaped
- **Defect versus Effort** -> Linear. Errors lead to defects at a relatively constant rate. Can adjust the slope of the line.
- **Defect versus Staffing** -> Rayleigh curve.
- **Defect versus Code Production Rate** -> Related to staff effort curve, follow Rayleigh curve.
- **Defect Density versus Module Complexity**
    - "bathtub chart"
    - **Defect Density :** The number of defects per KLOC or per function point.
    - Defect density for small module is high, falls exponentially as the size increases, bottoms out for a while, and then rises again.
    - Initial set of "startup defects" will create a high defect density for very small module.<br>As the software becomes increasingly complex, it causes a higher rate of defects.
    - <img src = "https://drive.google.com/uc?id=13KoD3IKOtQDwF68liRRXo8fcTCDZIgFq" alt = "Defect Dynamics Graph" align = "center" width="70%">

<br>

**🔥Defect Model**
- project the total number of defects and their distribution over time. Dynamic & Static.
- **Static model** 
    - uses attributes of the project and the process to predict the number of faults.
    - can be used early in the development process, even before the tracking of defects begin.
- **Dynamic model**
    - based on the statistical distribution of faults found.
    - require defect data and used once the tracking of defects starts.

<br>

**🔥Dynamic Defect Models**
- **Rayleigh, Exponential, S-curves** are defect distribution equations
- Rayleigh distributions model the entire development life cycle
- Exponential & S-curves are applicable for the testing/deployment processes
- **2 distribution functions**
    - Probability Distribution Function (**PDF**) for defect arrivals, called f(t)
    - Cumulative Distribution Function (**CDF**) for total number of defects to arrive by time t, called F(t)
    - f(t) is the derivative of F(t). `dF(t)/dt = f(t)`
- The Rayleigh and Exponential curves are both in the family of Weibull curves and have the forms<br>`f(t) = m(t/c)^m * e^(-t/c)^m / t`<br>`F(t) = 1 - e^(-t/c)^m`<br>For Exponential distribution, m = 1.<br>For Rayleigh distribution, m = 2.

<br>

**🔥Rayleigh Models**
- Equations for the basic Rayleigh curves:<br>`f(t) = K * 2(t/c)^2 * e^(-t/c)^2`<br>`F(t) = K * (1 - e^(-t/c)^2)`
- Here t is time, c is constant, and k is the total number of defects (area under the curve)
- use these equations to predict arrival rates and total number of defects.
- `c = √2 t_m`, where t_m is the time t at which f(t) is maximum
- 40% of the defects should appear by time t_m
- Predicting the distribution
    ```
    In Easy method, from defect arrival data, t_m is found.
    Find sum of the number of bugs from t_1 to t_m.
    Given 40% of the defects appear by t_m, total number of defects (k) can be found.
    f(t) can be found using k and t_m.
    ```
    ```
    In more complex method, calculate k using data points and t_m.
    Calculate K for all the values of f(t). That is in the equation, put f(t), t, t_m, e to find K.
    Calculate the mean and standard deviation for all values of k.
    ```

<br>

**🔥Static Defect Models**
- **Data Insertion and Removal Model**
    - Defects in : Requirement, Design, Coding
    - Defects out : Prototyping, Reviews, Inspections, Testing
    - Improve a product by inserting fewer defects, removing more of them.
    - Good high-level model to guide thinking and reason about defect processes.
- **Defect Removal Efficiency (DRE)**
    - `DRE_i = E_i / (E_i + E_i+1)`
    - E_i is the number of defects found in the activity i
    - E_i+1 is the number of defects found after activity i that are traceable to defects that were present during activity i.
    - The goal is to have DRE_i approach 1, so that defects are found and removed before they reach the next activity.
    - The **defect removal matrix** is a useful matrix that identifies both the phase in which a defect was inserted and when it was removed.
        - can calculate the efficiencies of the defect removal for each step in a process.
        - **Four defect removal steps :** Requirements Review, Design Review, Testing and Customer Detected
        - **Three defect insertion phases :** Requirements, Design and Coding.
        - Representing defect data in a DRE matrix: 
        <table>
            <tr>
                <td colspan="4" align="right"><strong>Defect Injection Phase</strong></td>
            </tr>
            <tr>
                <td><b>Defect Removal Step</b></td>
                <td align="center"><b>Requirements</b></td>
                <td align="center"><b>Design</b></td>
                <td align="center"><b>Coding</b></td>
                <td align="center"><b>Total</b></td>
            </tr>
            <tr>
                <td><b>Requirements Review</b></td>
                <td align="center">13</td>
                <td align="center"></td>
                <td align="center"></td>
                <td align="center">13</td>
            </tr>
            <tr>
                <td><b>Design Review</b></td>
                <td align="center">2</td>
                <td align="center">12</td>
                <td align="center"></td>
                <td align="center">14</td>
            </tr>
            <tr>
                <td><b>Testing</b></td>
                <td align="center">3</td>
                <td align="center">5</td>
                <td align="center">32</td>
                <td align="center">40</td>
            </tr>
            <tr>
                <td><b>Customer Detected</b></td>
                <td align="center">1</td>
                <td align="center">3</td>
                <td align="center">4</td>
                <td align="center">8</td>
            </tr>
            <tr>
                <td><b>Total</b></td>
                <td align="center">19</td>
                <td align="center">20</td>
                <td align="center">36</td>
                <td align="center">75</td>
            </tr>
        </table>
        
        - The matrix indicates that 19 requirements defects have been found, 13 of which were found in the requirements review, 2 in design review, 3 in testing, and 1 by the customer.
        - DRE for System = Total Detected Before Release / Total Detected
= 67 / 75 = 89%
        - DRE of a phase measures the percentage of possible faults that were removed in a phase.
        - In design, there were 26 possible faults that could have been detected (6 requirements & 20 design faults)<br>14 of them were discovered in the design review phase, resulting in a DRE of 14/26 
        - DRE_requirement = 13 / 19 = 68%
        - DRE_design = 14 / 26 = 54%
        - DRE_testing = 40 / 48 = 83%
        - DRE_customer-detected = 8 / 8 = 100%
        ```
        Cost of fixing in req/design -> 1x
        Cost of fixing in coding -> 5x
        Cost of fixing in formal testing phase -> 25x
        Cost of fixing in field -> 250x

        A DRE of 100% is probably impossible due to latent defects.
        Good software should be less than 2 defects per KLOC.
        Safe software should be 0.5 - 1.5 defects per KLOC.
        ```

</details>