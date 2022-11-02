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

<h2>**<u>Previous Lecture</u>**</h2>

<details><summary><h2>Lecture-01: 22nd August, 2022</h2></summary>

- What is OS?

</details>

<details><summary><h2>Lecture-02: 30th August, 2022</h2></summary>

- Operating System Service
- System Call Implementation
- Api - System Call - Os relationship
- System Call Parameter Passing
- <details><summary>Types of System Call</summary>

    - Process Control
    - File Management
    - Device Management
    - Information Maintainance
    - Communications
    - Protection
    </details>
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


................................................................................................................................

<h2>**<u>New Lecture</u>**</h2>

<details><summary><h2>Lecture-01: 11th October, 2022</h2></summary>

Instruction for system.

Program
- Data: data management
- Code: data processing

Resource - Memory, Program<br>
Memory - Active, Passive.

Safety
- Overall System
- Individual (Program level)

Input depends on user, output depends on system.<br>
Programs becom slow if IO instructions are more.<br>

While saving file, size = content + basic properties.

If txt file is converted to docx file, size increases even more, as each character has font, color etc metadata.

In case of process also, properties of process(state, register) needs to be preserved.

Did process quit wiliingly or forcefully interrupted?

Interrupt when process with more property comes, or in Round Robin when time slice is over.

Program is in disk. Need reference of it.
Context switching needs time.

Each file has minimum size even without content.

To mitigate CPU-Memory gap: Cache management - Cache Organize for faster access.

Memory management is everything.
</details>

<details><summary><h2>Lecture-02: 18th October, 2022</h2></summary>

<b>Process Switching</b>

Housekeeping Task done by OS (Overhead for System)<br>
The more task & resource used, the more time to switch process.

Cpu is working, though from user perspective, it seems idle.

Background - System(OS)

Utility - Antivirus<br>
Application Software, garbage collector

These are background for me, but foreground for system.

Not all job are same, neither their purpose.

If one file of 20 mb is sent 5 times, total sent 100mb.<br>
But Throughput is 20mb - the amount done.
<br>Throughput is efficiency. If output increae, so does throughput.

<b>ToDo: Ctrl + Alt + Del</b>

Scheduler maintains process to be assigned to CPU
<br>CPU needs to remain busy. So, push process in ready queue.

<b>Long Term Scheduler</b> assign process.

<b>Degree of MultiProgramming</b>

Though storage is increasing, complexity of process also increases.

For that, MidTerm Scheduler.

Batch file - Job File
exe File - Program File

</details>

<h2>Lecture-03: 20th October, 2022</h2>

Online class

<details><summary><h2>Lecture-04: 25th October, 2022</h2></summary>

<blockquote>
Process may be dependent or independent. If dependent, need to share data.
<br>If writing is not complete, giving read mode can cause inconsistenct data to be read.

Code sharing easy. Data sharing complicated.
</blockquote>

<details><summary><b>Corporating Process</b></summary>

- Information sharing - Global Var.
- Computation Speed up - Merge Sort.
- Modularity - define in sub task (part of program).
- Convenience - Data one, sharing with all.
</details>
<br>
If write mode access is given to multiple process, need to keep track and combine them, increase in complexity.

<br>
<details><summary><b>Producer - Consumer [Handshaking]</b></summary>

- Use Buffer
- Bounded: Array
- Unbounded: List Types whose memory are dynamically allocated
</details>
<br>
All output device Consumer, all input are producer.

<b>Interprocess Communication</b>
- Parameter Passing
- Message sharing

<details><summary><b>Remote</b></summary>

- network
- Unique Identification (URL)

<blockquote>
Each process has process ID. But it is local to machine.
<br>My Pc is destination. All different tabs are process.

Via IP, network is detected. IPV4: 32bit, IPV6: 128bit
<br>Then service based Id. Now nearly all program are network oriented.
</blockquote>
</details>

<details><summary><b>Browsing</b></summary>

<blockquote>
Via Terminal, Technical browsing.<br>
Browser provides internet service.

Https, Ftp are different service. Browser provides them.

File if not fully downloaded, cannot be viewed.
<br>But, web page can be viewed - the amount that has been loaded.

WPS app provides browsing capability.
</blockquote>
</details>
<br>

<b>Web server:</b> make environment/platform ready. 
Server needs to host service that it wishes to provide.

<details><summary><b>Socket = IP + Port Number </b></summary>

IP ~ digit (low level), DNS ~ Name (high level)

- MAC (easy for machine)
- IP
- DNS (easy for me)
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

<br><br>
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