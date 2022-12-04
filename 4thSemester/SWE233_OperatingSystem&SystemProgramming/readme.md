<h1 align="center">Operating System and System Programming</h1>
<h3 align="center"> <a href="https://drive.google.com/drive/u/0/folders/1ipS8U50KywocfKG1-dZfjWogO1PYDndL" title="Drive Link of OS"><ins>Drive Link</ins></a> </h3>

<h2>Resource:</h2>

[fba13](https://www.youtube.com/watch?v=tBVWKGBAeQ8&list=PLJW6cU20q-SNCeRTbz3gOO6MMJb5C3tNO)

[Neso Academy](https://www.youtube.com/watch?v=vBURTt97EkA&list=PLBlnK6fEyqRiVhbXDGLXDk_OQAeuVcp2O)

[Hamid Mukhtar](https://www.youtube.com/playlist?list=PLBpMYKycVdGb3tlVlmR9Rmx47p6UOVp7W)

<h2>Book:</h2>

**Operating System Concepts** - 10th Edition

by Abraham Silberschatz, Peter Baer Galvin, Greg Gagne
<br><br>

<h2 align="center"><u><b>Previous Lecture</b></u></h2>

<details><summary><h2>Lecture-01: 22nd August, 2022</h2></summary>

- What is OS?

</details>

<details><summary><h2>Lecture-02: 30th August, 2022</h2></summary>

- Operating System Service
- System Call Implementation
- Api - System Call - Os relationship
- System Call Parameter Passing
- Types of System Call
    - Process Control
    - File Management
    - Device Management
    - Information Maintainance
    - Communications
    - Protection
- System Programs
- Operating System Design and Implementation

</details>

<details><summary><h2>Lecture-03: 5th September, 2022</h2></summary>

<b>Process</b>
- <details><summary>Concepts</summary>

    - Process is a program in execution, process execution must progress in sequential fashion. Process has multiple parts:
        - Program Code
        - Program Counter
        - Stack containing temp data
        - Data section containing Global Variables
        - Heap containing memory dynamically allocated during runtime
    </details>
- <details><summary>State</summary>

    - New: Process being created
    - Running: Instructions being executed
    - Waiting: for some event to occur
    - Ready: ready to be assigned to a processor
    - Terminated: the process has finished execution

    New, Ready state: waiting for CPU<br>
    Waiting state: for others
    </details>
- <details><summary>Task Control Block(PCB)</summary>

    - State
    - Program Counter: Location of the next instruction to be executed.
    - CPU Register: Contents of all process-centric registers.
    - CPU Scheduling Information: Priorities, Scheduling queue pointers
    - Memory Management Information: Memory allocated to the process.
    - Accounting Information: CPU used, clock time elapsed since start, time limits.
    - I/O status Information: I/O device allocated to process, list of open files.
    </details>
- <details><summary>Threads</summary>

    - So far, process has single thread of execution
    - If multiple program counter per process.
        - Multiple locations can execute at once.
        - Multiple threads of control.
        - Save thread details.
    </details>
- Process Scheduling
    - Maximize CPU use, quickly switch processes onto CPU for time sharing.
- <details><summary>Multiprocess Architecture</summary>

    - Google Chrome Browser is multiprocess with 3 categories
        - Browser Process
        - Render Process
        - Plug-in Process
    </details>
- Interprocess Communication
    - Shared Memory
    - Message Queue
- Cooperating Process


</details>

<h2 align="center"><b><u>New Lecture</u></b></h2>

<details><summary><h2>Lecture-01: 11th October, 2022</h2></summary>

<details><summary><b>Program</b></summary>

- Data: data management
- Code: data processing

<blockquote>
Program is in disk. Need reference of it.<br>
Programs becomes slow if IO instructions are more.

Resource - Memory, Program<br>
Memory - Active, Passive.<br>
Input depends on user, output depends on system.
</blockquote>
</details>

<details><summary><b>Safety</b></summary>

- Overall System
- Individual (Program level)
</details>

<details><summary><b>File Size</b></summary>

- File size = content + basic properties.
- Txt file -> docx file, size ↑ (metadata of each character - font, color etc.)
- Each file has minimum size even without content.
</details>

<details><summary><b>Process</b></summary>

<blockquote>
Did process quit wiliingly or forcefully interrupted?<br>
Interrupt when process with more priority comes, or in Round Robin when time slice is over.

Properties of process(state, register) needs to be preserved.<br>
Context switching needs time.
</blockquote>
</details>

Cache management
- To mitigate CPU-Memory gap:
- For faster access.

Memory management is everything.
</details>

<details><summary><h2>Lecture-02: 18th October, 2022</h2></summary>

<details><summary><b>Process Switching</b></summary>

<blockquote>
Housekeeping Task done by OS (Overhead for System)<br>
The more task & resource used, the more time to switch process.

Cpu is working, though from user perspective, it seems idle.<br><br>
Background: System(OS)<br>
Utility(anitvirus) & application software are background for user, but foreground for system.
</blockquote>
</details>

<details><summary><b>Throughput</b></summary>

<blockquote>
Not all job are same, neither their purpose.<br><br>
If one file of 20 mb is sent 5 times, total sent 100mb.<br>
But Throughput is 20mb - the amount done.
<br>Throughput is efficiency. If output increase, so does throughput.
</blockquote>
</details>

<details><summary><b>Assigning Process</b></summary>

<blockquote>
CPU needs to remain busy. So, push process in ready queue.<br>
Scheduler maintains process that will be assigned to CPU.

<b>Long Term Scheduler</b> assign process.

Though storage is increasing, complexity of process also increases.<br>
For that, MidTerm Scheduler.
</blockquote>
</details>

<b>Degree of MultiProgramming</b>

> Batch file - Job File<br>
> Exe File - Program File

<b>Try: Ctrl + Alt + Del</b>

</details>

<details><summary><h2>Lecture-03: 20th October, 2022</h2></summary>

***Online class***

**Representation of Process Scheduling**

<details><summary><b>Context Switch from Process to Process</b></summary>

* Either task done
* Alotted time slot is over
* Interrupted due to high priority process

>If context switch decreases, throughput increases.
</details>


**Multitasking** & **MultiProgramming** in chapter 1

<details><summary><b>Operations on Processes</b></summary>

 * Process Creation
 * Process Termination

>Process creation request by user or a process itself. Created by OS.<br>
>Each process is identified by Process ID.
</details>

<details><summary><b>Resource</b></summary>

>Resource may be logical (files) or physical (hardware)<br>
>Each process needs at least one resource -> CPU.
><br>Resource is limited. So it may be shared.

>Parent & Child may share resources.
><br>File reading may be done by many, but writing is complicated.

</details>

<details><summary><b>Dependency</b></summary>

>Same browser, multiple tab. No dependency
><br>Tab in same or different window. Multiple process.

>If dependency, parent waits until child terminates. Orderly termination.<br>
>Github Desktop(parent) authentication via Chrome(child). After that no dependency. Dependency for short time.
<br>

</details>

<details><summary><b>Process Terminaiton</b></summary>

>exit() -> terminate program.<br>
>return -> terminate the current block/module.

>**Abnormal Termination**<br>
>OS is parent. If any child process exceed allocated resources,<br> no longer required, parent terminated, infinity running etc. abnomal behaviour then abort().

>**Cascading Termination**<br>
>All children, grandchildren etc. are terminated.<br>
>ZOMBIE -> no parent<br>
>ORPHAN -> parent terminated
</details>

<details><summary><b>Multiprocess Architecture - Chrome Browser</b></summary>

* Browser
* Renderer (Sandbox -> a virtual environment to run program with restricted features. To test 3rd party software. `Safe mode` in Windows)
* Plug-in

>Sanbox itself is a program. It's a multiprocess architecture.

>Tab -> Convenient for user, Multiple instance of a process, independently run.

>Now-a-days, Editor, IDE multiprocess. In one environment, different facilities.
</details>

<details><summary><b>Interprocess Communication</b></summary>

**Cooperation**
* Orderly like function call.//dependency,, can't execute unless other part is finished.
* Concurrently like merge sort. //can execute simultaneously.

**Dependency to**
* share info
* speedup
* modularity
* convenience

**Two models of IPC**
* Shared memory
* Message passing

</details>

**Kernel**<br>


**Ques: Memory cell of 1000 size array is in same place or not?**
</details>

<details><summary><h2>Lecture-04: 25th October, 2022</h2></summary>

<details><summary><b>Process Dependency</b></summary>

<blockquote>
Process may be dependent or independent. If dependent, need to share data.<br>
Code sharing easy, data sharing complicated.<br>
<br>If writing is not complete, giving read mode access can cause inconsistenct data to be read.<br>
<br>
If write mode access is given to multiple process, need to keep track and combine them. Complexity increases.
</blockquote>
</details>

<details><summary><b>Co-operating Process</b></summary>

- Information sharing - Global Variable.
- Computation Speed up - Merge Sort.
- Modularity - define in sub task (part of program).
- Convenience - Single data, sharing with all.
</details>

<details><summary><b>Producer - Consumer [Handshaking]</b></summary>

- Use Buffer
- Bounded: Array
- Unbounded: List, memory that are dynamically allocated

> All output devices are Consumer, all input devices are Producer.
</details>

<b>Interprocess Communication</b>
- Parameter Passing
- Message sharing

<details><summary><b>Remote</b></summary>

- network
- Unique Identification (URL)

<blockquote>
Each process has process ID. But it is local to machine.
<br>User Pc is destination. All different tabs are process.

Via IP, network is detected. IPV4: 32bit, IPV6: 128bit
<br>Then service based Id. Now nearly all program are network oriented.
</blockquote>
</details>

<b>Web server:</b>
> Makes environment/platform ready.<br>
> Server needs to host service that it wishes to provide.

<details><summary><b>Browsing</b></summary>

<blockquote>
Via Terminal, Technical browsing.<br>
Browser provides internet service.

Https, Ftp are different service. Browser provides them.

If file is not fully downloaded, it cannot be viewed.
<br>But, web page can be viewed - the portion that has been loaded.

`WPS` app provides browsing capability.
</blockquote>
</details>

<details><summary><b>Socket = IP + Port Number </b></summary>

IP ~ digit (low level), DNS ~ Name (high level)

- MAC (easy for machine)
- IP
- DNS (easy for user)
</details>

</details>

<h2>Lecture-05: 27th October, 2022</h2>

Online class

<details><summary><h2>Lecture-06: 1st November, 2022</h2></summary>

<b>Chapter 5: CPU Scheduling</b>

<b>Priority Scheduling</b>

To shutdown PC
- Command line/gui/ctrl+alt+f4
- Pull out cable
- Press Power Button (works in micro-processor level)

Aging:

- Waiting process will get chance, as their priority increases as time increases.

<b>Example of Priority Scheduling</b>

<details><summary><b>Round Robin</b></summary>

- Time Quantum
- n process after n iterations will get 1 chance
- Waiting time is distributed, Response time better
- If the only process in a queue needs 12 unit time & slot for each process is 2 unit, the process will be assigned 6 times. Though it is ok if task switching is negligible.
</details>

<br>
All methods has advantage & disadvantages

First Come First Service
- Simplistic, no calculation required. All rest methods need to manage, monitor, calculate.

Round Robin
- After time limit is over, should the process be assigned again or is it done? Willingly replace or not?

<b>Define appropriate Priority Scheduling</b>

<b>Multi-level Queue</b>

Foreground - RR (User process, Response important, so RR method important, all rest method will increase waiting time.)

Background - FCFS (All task are of similar level, length. Scope to justify if methods other than FCFS is used.)

Explain logically your opinion.
Whether you agree or not?

Some System Process

- memory allocoate
- invalid operation
- garbage collection

here priority of invalid operation is most.
<br>Garbage collection depends on situation.
<br>Invalid operation is checked always.

So these are in different queue. If in same queue, different priority.

<b>NEXT CLASS: QUIZ on PROCESS. 20 marks</b>

</details>

<h2>Lecture-07: 3th November, 2022</h2>

- Online Class

<h2>Lecture-08: 8th November, 2022</h2>

- TT postponed
- Deadlock
- 4 characteristics
- Resource allocation graph etc. detailed discussion

<h2>Term Test-1: 15th November, 2022</h2>

- Process

<h2>Lecture-09: 23th November, 2022</h2>

- Circular Wait
- Safe State
- Deadlock Avoidance
- R2 -> T1 -> R1 (R2 is allocated to T1 process, T1 is waiting for R1 process)
- If multiple instance of resource, apply Banker Algorithm.<br><br>
- **Task:** Resource Allocation Graph
- **Reminder:** Ch1, Ch2
- **Lab:** Code in Linux

<h2>Lecture-10: 30th November, 2022</h2>

- Online Class 10 minute
- Deadlock Detection

<h2>Lecture-11: 4th November, 2022</h2>

- Deadlock chapter completed
- Memory Management

<h2>Lecture-12: 5th November, 2022</h2>