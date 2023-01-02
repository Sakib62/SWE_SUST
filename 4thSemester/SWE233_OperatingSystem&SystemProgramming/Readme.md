<h1 align="center">Operating System and System Programming</h1>

<b>Resource:</b>

[fba13](https://www.youtube.com/watch?v=tBVWKGBAeQ8&list=PLJW6cU20q-SNCeRTbz3gOO6MMJb5C3tNO), 
[Neso Academy](https://www.youtube.com/watch?v=vBURTt97EkA&list=PLBlnK6fEyqRiVhbXDGLXDk_OQAeuVcp2O), 
[Hamid Mukhtar](https://www.youtube.com/playlist?list=PLBpMYKycVdGb3tlVlmR9Rmx47p6UOVp7W)

<b>Book:</b>

[Operating System Concepts - 10th Edition](Books/Operating_System_Concepts_10E.pdf)
<br><br>

<h2 align="center"><u><b>Previous Lecture</b></u></h2>

<br><h2><u>Lecture-01: 22nd August, 2022</u></h2>

- What is OS?

<br><h2><u>Lecture-02: 30th August, 2022</u></h2>

- Operating System Service
- System Call Implementation
- API - System Call - OS relationship
- System Call Parameter Passing
- Types of System Call
    - Process Control
    - File Management
    - Device Management
    - Information Maintenance
    - Communication
    - Protection
- System Program
- Operating System Design and Implementation

<br><h2><u>Lecture-03: 5th September, 2022</u></h2>

<b>Process</b>

1. **Concepts**
    - Process is a program in execution, process execution must progress in sequential fashion. Process has multiple parts:
        - Program Code
        - Program Counter - Location of the next instruction to be executed.
        - Stack containing temp data
        - Data section containing Global Variables
        - Heap containing memory dynamically allocated during runtime

2. **State**
    - New - Process being created
    - Running - Instructions being executed
    - Waiting - for some event to occur
    - Ready - ready to be assigned to a processor
    - Terminated - the process has finished execution

    <br>New & Ready state is waiting for CPU<br>
    Waiting state is for others

<br>

3. **Process / Task Control Block(PCB)**

    - State
    - Program Counter
    - CPU Register - Contents of all process-centric registers.
    - CPU Scheduling Information - Priorities, Scheduling queue pointers
    - Memory Management Information - Memory allocated to the process.
    - Accounting Information - CPU used, clock time elapsed since start, time limits.
    - I/O Status Information - I/O device allocated to process, list of open files.

4. **Threads**
    - If multiple program counter per process.
        - Multiple locations can execute at once.
        - Multiple threads of control.
        - Save thread details.

5. **Process Scheduling**
    - Maximize CPU use
    - Quickly switch processes onto CPU for time sharing.

6. **Multiprocess Architecture**
    - Google Chrome Browser is multiprocess
        - Browser Process
        - Render Process
        - Plug-in Process

7. **InterProcess Communication**
    - Shared Memory
    - Message Queue

<br><h2 align="center"><b><u>New Lecture</u></b></h2>

<br><h2><u>Lecture-01: 11th October, 2022</u></h2>

<b>Program</b>
- Data - managing data
- Code - processing data
- Remains in disk. Need reference of it
- Becomes slow if IO instructions are more

<b>Safety</b>
- Overall System
- Individual (Program level)

<b>File Size</b>

- File Size = Content + Basic Properties
- Each file has minimum size even without content
- If Txt file -> docx file, size increases as metadata of each character - font, color etc. are needed to be stored.

<b>Process</b>

- Pre-emptive (by Force) or Non-preemptive Termination
- Interrupted if high priority process arrives
- Interrupted if time slice is over in Round Robin scheduling
- Properties of process(state, register) is saved in PCB
- Context Switching needs time.

<b>Cache management</b>
- To mitigate CPU-Memory gap
- For faster access.

<br><h2><u>Lecture-02: 18th October, 2022</u></h2>

<b>Process Switching</b>
- Housekeeping Task done by OS. It is a Overhead for System.
- The more task & resource is used, the more time to switch process.
- Cpu is working, though from user perspective, it seems idle.
- Utility & Application software are background for user, but foreground process for system.

<b>Throughput</b>

- Not all job are same, neither their purpose.
- If one file of 20 mb is sent 5 times, total sent 100mb.
But Throughput is 20mb - the amount done.
- Throughput is a measure of how many units of information a system can process in a given amount of time.

<b>Assigning Process</b>

- CPU needs to remain busy. So, push process in Ready Queue.
- Scheduler maintains process that will be assigned to CPU.
- Long Term Scheduler assigns process.
- Though storage is increasing, complexity of process is also increasing. Sometimes memory need to be freed.
- **MidTerm Scheduler** reduces **Degree of MultiProgramming.**<br>
It swaps out process from memory to disk and Swaps in from disk if needed.

<b>Try: Ctrl + Alt + Del</b>

<br><h2><u>Lecture-03: 20th October, 2022</u></h2>

`Online class`

Representation of Process Scheduling

<b>1. Context Switch</b>
* Either task done or alotted time slot is over
* Interrupted due to high priority process
* If context switch decreases, throughput increases.

<b>2. Operations on Process</b>
 * Process Creation - request by user or another process.<br>Created by OS. Each process is identified by Process ID.
 * Process Termination

<b>3. Resource</b>

- Logical (files) or Physical (hardware)
- Each process needs at least one resource -> CPU.
- Resource is limited. So it may be shared.
- Parent & Child may share resources.
- File reading may be done by many, but writing is complicated.

<b>4. Dependency</b>
- Same browser, multiple tab. No dependency. Multiple instance of a process, independently run.
- Tab in same or different window. Multiple process.
- If dependency exists, parent waits until child terminates. Orderly termination.
- Github Desktop (parent) authentication via Chrome (child). Dependency for short time.

<b>5. Process Terminaiton</b>
- exit() -> terminate program.
- return -> terminate the current block/module.
- **Abnormal Termination**
    - If any child process exceeds allocated resources / no longer required / parent terminated / infinitely running etc. abnomal behaviour then abort().
- **Cascading Termination**
    - All children, grandchildren etc. are terminated.
    - ZOMBIE -> no parent
    - ORPHAN -> parent terminated

<b>6. Multiprocess Architecture - Chrome Browser</b>

* Browser, Renderer, Plug-in
* Sandbox is a virtual environment to run program with restricted features, to test 3rd party software. In Windows, "Safe Mode"

<b>7. Inter Process Communication (IPC)</b>

- Cooperation 
    * Orderly such as function call. Can't execute unless other part is finished.
    * Concurrently like merge sort. Can execute simultaneously.
* Dependency for sharing info, speedup, modularity, convenience
* Two models of IPC
    * Shared memory
    * Message passing

**Question:** Memory cell of 1000 size array is in same place or not?

**MultiTasking** & **MultiProgramming** in chapter 1

<br><h2><u>Lecture-04: 25th October, 2022</u></h2>

<b>Process Dependency</b>

- Dependent process need to share data. Code sharing is easy, data sharing is complicated.
- If writing is not complete, giving read access can cause inconsistenct data to be read.
- If write access is given to multiple process, need to keep track and combine them. Complexity increases.

<b>Co-Operating Process</b>

- Information Sharing - Global Variable.
- Computation Speed up - Merge Sort.
- Modularity - Sub-Task.
- Convenience - Single data, sharing with all.

<b>Producer - Consumer [Handshaking]</b>

- Use Buffer
- Bounded: Array
- Unbounded: Memory that are dynamically allocated such as List
- All output devices are Consumer. All input devices are Producer.

<b>Remote</b>

- Network -> detected via IPV4: 32bit, IPV6: 128bit. Then server based id. Process ID is local to machine.<br>Now-a-days, nearly all programs are network oriented.

- Unique Identification (URL)

<b>Web server:</b>
- Makes environment / platform ready.<br>
- Server needs to host service that it wishes to provide.

<b>Browsing</b>

- Via Terminal, Technical browsing.<br>
- Browser provides internet service.
- Https, Ftp are different service. Browser provides them.
- If file is not fully downloaded, it cannot be viewed.
<br>But, web page can be viewed - the portion that has been loaded.
- `WPS` app provides browsing capability.

<b>Socket = IP + Port Number </b>

- MAC (easy for machine)
- IP (digit, low level)
- DNS (name, easy for user, high level)

<br><h2><u>Lecture-05: 27th October, 2022</u></h2>

`Online class`

**Chapter 5: CPU Scheduling**
- Basic Concepts
- CPU Scheduler
- Preemptive & Non-preemptive Scheduling
- Scheduling Criteria
- First Come, First Served (FCFS) Scheduling
- Shortest Job First (SJF)
- Round Robin

<br><h2><u>Lecture-06: 1st November, 2022</u></h2>

<b>Chapter 5: CPU Scheduling</b>

**Starvation:** 
- In Process Scheduling, some process may never get access to CPU. 

**Aging:** 
- Priority is associated with each process.
- Priority of waiting process will increase as time increases.
So, they will get a chance.

<b>Round Robin Scheduling</b>

- Time Quantum
- n process after n iterations will get 1 chance
- Waiting time is distributed, Response time better
- If the only process in a queue needs 12 unit time & slot for each process is 2 unit, the process will be assigned 6 times. Though it is ok if task switching is negligible.

**Advantage & Disadvantages**

1. First Come First Service
    - Simplistic, no calculation required. All rest methods need to manage, monitor, calculate.
2. Round Robin
    - After time limit is over, should the process be assigned again or is it done? Willingly replace or not?

<b>Analytical Question:</b> Define appropriate Priority Scheduling. Explain your answer with logic.
1. Foreground / User Process
    - Round Robin (Response important. Waiting time is more in other methods.)
2. Background Process
    - FCFS (All task are of similar level, length. Justify if other methods are used.)

**Question:** Do you agree or not?

<b>Multi-Level Queue</b>

- Process with different priority level is in different queue.

Among some System Process - Memory Allocation, Invalid Operation, Garbage Collection; priority of invalid operation is most, it is checked always. Garbage collection depends on situation.

<br><h2><u>Lecture-07: 3rd November, 2022</u></h2>

`Online Class`

CPU Scheduling

- Multi-Level Queue
- Multi-Level Feedback Queue
- Multiple-Processor Scheduling
- Real-Time CPU Scheduling
- Priority-based Scheduling
- Real Monotonic Scheduling
- Linux Scheduling

Deadlock
- Characterization
- Resource-Allocation Graph
- Methods for handling deadlock

<br><u><h2>Lecture-08: 8th November, 2022</u></h2>

- Deadlock - 4 characteristics
- Resource Allocation Graph - cycle, instance of resources

<br><u><h2>Lecture-09: 23rd November, 2022</u></h2>

- Circular Wait
- Safe State
- Deadlock Avoidance
- R2 -> T1 -> R1 (R2 is allocated to T1 process, T1 is waiting for R1 resource)
- If multiple instance of resource, apply Banker Algorithm.<br><br>
- **Task:** Resource Allocation Graph
- **Reminder:** Chapter 1, Chapter 2
- **Lab:** Code in Linux

<br><h2><u>Lecture-10: 30th November, 2022</u></h2>

`Online Class` short duration
- Deadlock Detection

<br><h2><u>Lecture-11: 4th December, 2022</u></h2>

- Deadlock Revised
- Memory Management

<br><h2><u>Lecture-12: 5th December, 2022</u></h2>

- Memory Management

<br><h2><u>Lecture-13: 7th December, 2022</u></h2>

- Memory Management

<br><h2><u>Lecture-14: 11th December, 2022</u></h2>

`Online Class`

- Chapter 1 & 2
- Introduction to OS

<br><h2><u>Lecture-15: 23rd December, 2022</u></h2>

`Online Class`

- Paging, Fragmentation
- Implementation & Structure of Page Table

<br><h2><u>Lecture-16: 27th December, 2022</u></h2>

`Online Class`

- Paging
- Virtual Memory 

<br><h2><u>Lecture-17: 29th December, 2022</u></h2>

`Online Class`

- Virtual Memory

<br><h2><u>Lecture-18: 30th December, 2022</u></h2>

`Online Class`

- Virtual Memory

<br><h2><u>Lecture-19: 31st December, 2022</u></h2>

`Online Class`

- [Term Test](Exam.md) Question Discussion