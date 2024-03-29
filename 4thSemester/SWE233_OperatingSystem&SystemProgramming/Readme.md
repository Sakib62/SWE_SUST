<h1 align="center">Operating System and System Programming</h1>

<b>Book :</b>
- Operating System Concepts - Silberschatz - 10th Edition
- Operating Systems in Depth - Thomas W Doeppner

[✅**Book Link**][book]

[book]: https://drive.google.com/drive/folders/1rV4ZqCYzchrtlv3dvJz47bAeiR9RauN0?usp=share_link

<br>

<b>Resource :</b>
- Slides of Operating System Concepts

[✅**Resource Link**][res]

[res]: https://drive.google.com/drive/folders/1mb5UZ2lRtG5GdpaWPeFZgsAZRTzXqF79?usp=share_link

<br>

<b>Youtube Playlist :</b>
- [Neso Academy](https://www.youtube.com/playlist?list=PLBlnK6fEyqRiVhbXDGLXDk_OQAeuVcp2O) + [fba13](https://www.youtube.com/playlist?list=PLJW6cU20q-SNCeRTbz3gOO6MMJb5C3tNO)
- [Lecturelia](https://www.youtube.com/playlist?list=PLncy2sD7w4Yr3ZbiP_ipAjgjDRn86N_tT)
- [Gate Smashers](https://www.youtube.com/playlist?list=PLxCzCOWd7aiGz9donHRrE9I3Mwn6XdP8p)
- [Farhan Hossan](https://www.youtube.com/playlist?list=PLgrAmbRAezujiknEO3sqpyCC4K3IgS4KU)
- [Hamid Mukhtar](https://www.youtube.com/playlist?list=PLBpMYKycVdGb3tlVlmR9Rmx47p6UOVp7W) etc.

<br><b>⭐TT & Previous Year Question :</b> [Click Here](Exam.md)<br>

<br><b>⭐Chapters :</b>  
- Chapter 1: Introduction
- Chapter 2: Operating System Services (System Call, System Services, Architecture -> monolithic, layered - pros & cons))
- Chapter 3: Processes (Skip slides related to -> Linux, Example code in C, Fork, POSIX, Mach)
- Chapter 5: CPU Scheduling
- Chapter 8: Deadlocks (All Slide)
- Chapter 9: Main Memory
- Chapter 10: Virtual Memory (Up to 45th Slide + Thrashing)


>Go through Slides, Watch Recorded Class, YT video.<br>
Practise Math -> Page Table, Banker Algorithm, Scheduling Algorithm.

<br>

<details><summary><h2><u><b>Previous Lecture (Total : 3)</b></u></h2></summary>

<br><h2><u><strike>Lecture-01: 22nd August, 2022</strike></u></h2>

<b>✨Chapter - 1: Introduction✨</b>
- What is OS?

<br><h2><u><strike>Lecture-02: 30th August, 2022</strike></u></h2>

<b>✨Chapter - 2: Operating System Services✨</b>

- System Call Implementation
- API - System Call - OS relationship
- System Call Parameter Passing
- Types of System Call ⭐Process Control, File Management, Device Management, Information Maintenance, Communication, Protection⭐
- System Program
- Operating System Design and Implementation

<br><h2><u><strike>Lecture-03: 5th September, 2022</strike></u></h2>

<b>✨Chapter - 3: Process✨</b>

1. Concepts
    - A program in execution, progress in sequential fashion. Process has multiple parts:
        - Program Code
        - Program Counter - Location of the next instruction to be executed.
        - Stack containing temp data
        - Data section containing Global Variables
        - Heap containing memory dynamically allocated during runtime

2. State
    - New - Process being created
    - Running - Instructions being executed
    - Waiting - for some event to occur
    - Ready - ready to be assigned to a processor
    - Terminated - the process has finished execution

    >New & Ready state is waiting for CPU<br>
    Waiting state is for others

3. Process / Task Control Block(PCB)
    - State
    - Program Counter
    - CPU Register - Contents of all process-centric registers.
    - CPU Scheduling Information - Priorities, Scheduling queue pointers
    - Memory Management Information - Memory allocated to the process.
    - Accounting Information - CPU used, clock time elapsed since start, time limits.
    - I/O Status Information - I/O device allocated to process, list of open files.

4. Process Scheduling
    - Maximize CPU use
    - Quickly switch processes onto CPU for time sharing.

5. Multiprocess Architecture
    - Google Chrome Browser is multiprocess ( Browser , Render , Plug-in

6. InterProcess Communication
    - Shared Memory
    - Message Queue

</details>

<hr>

<br><h2 align="center"><b><u>New Lecture (Total : 21)</u></b></h2>

<br>*Chapter 1 & 2 are covered in 1 lecture each.*<br>
*Other Chapters are covered in 3 to 4 lectures.*<br>
*Question Discussed in 1 lecture.*

9 Offline + 12 Online = 21 Lectures Total

<br><h2><u>Lecture-01: 11th October, 2022</u></h2>

<b>🔥Chapter - 3: Processes🔥</b>

1. Program
    - Data - managing data
    - Code - processing data
    - Remains in disk. Need reference of it
    - Becomes slow if I/O instructions are more
    - Safety
        - Overall System
        - Individual (Program level)
    - File Size
        - File Size = Content + Basic Properties
        - Each file has minimum size even without content
        - If Txt file -> docx file, size increases as metadata of each character - font, color etc. are needed to be stored.

2. Process
    - Pre-emptive (by Force) or Non-preemptive Termination
    - Interrupted if high priority process arrives
    - Interrupted if time slice is over in Round Robin scheduling
    - Properties of process(state, register) is saved in PCB
    - Context Switching needs time.
    - Cache management
        - To mitigate CPU-Memory gap
        - For faster access.

<br><h2><u>Lecture-02: 18th October, 2022</u></h2>

<b>🔥Chapter - 3: Processes🔥</b>

1. Process Switching
    - Housekeeping Task done by OS. It is a Overhead for System.
    - The more task & resource is used, the more time to switch process.
    - CPU is working, though from user perspective, it seems idle.
    - Utility & Application software are background for user, but foreground process for system.

2. Throughput
    - Throughput is a measure of how many units of information a system can process in a given amount of time.

3. Assigning Process
    - CPU needs to remain busy. So, push process in Ready Queue.
    - Scheduler maintains process that will be assigned to CPU.
    - Long Term Scheduler assigns process.
    - Though storage is increasing, complexity of process is also increasing. Sometimes memory need to be freed.
    - *MidTerm Scheduler* reduces *Degree of MultiProgramming.*<br>
    It swaps out process from memory to disk and Swaps in from disk if needed.

<i>Try: Ctrl + Alt + Del</i>

<br><h2><u>Lecture-03: 20th October, 2022</u></h2>

`Online class`

**🔥Chapter - 3: Processes🔥**

1. Context Switch
    * Either task done or alotted time slot is over
    * Interrupted due to high priority process
    * If context switch decreases, throughput increases.

2. Operations on Process
    * Process Creation - request by user or another process.<br>Created by OS. Each process is identified by Process ID.
    * Process Termination

3. Resource
    - Logical (files) or Physical (hardware)
    - Each process needs at least one resource -> CPU.
    - Resource is limited. So it may be shared.
    - Parent & Child may share resources.
    - File reading may be done by many, but writing is complicated.

4. Dependency
    - Same browser, multiple tab. No dependency. Multiple instance of a process, independently run.
    - Tab in same or different window. Multiple process.
    - If dependency exists, parent waits until child terminates. Orderly termination.
    - Github Desktop (parent) authentication via Chrome (child). Dependency for short time.

5. Process Terminaiton
    - exit() -> terminate program.
    - return -> terminate the current block/module.
    - *Abnormal Termination*
        - If any child process exceeds allocated resources / no longer required / parent terminated / infinitely running etc. abnomal behaviour then abort().
    - *Cascading Termination*
        - All children, grandchildren etc. are terminated.
        - ZOMBIE -> no parent
        - ORPHAN -> parent terminated

6. Multiprocess Architecture - Chrome Browser
    * Browser, Renderer, Plug-in
    * Sandbox is a virtual environment to run program with restricted features, to test 3rd party software. In Windows, "Safe Mode"

7. Inter Process Communication (IPC)
    - Cooperation 
        * Orderly such as function call. Can't execute unless other part is finished.
        * Concurrently like merge sort. Can execute simultaneously.
    * Dependency for sharing info, speedup, modularity, convenience
    * Two models of IPC
        * Shared memory
        * Message passing

*Question:* Memory cell of 1000 size array is in same place or not?

*MultiTasking* , *MultiProgramming*

<br><h2><u>Lecture-04: 25th October, 2022</u></h2>

**🔥Chapter - 3: Processes🔥**

1. Process Dependency
    - Dependent process need to share data. Code sharing is easy, data sharing is complicated.
    - If writing is not complete, giving read access can cause inconsistenct data to be read.
    - If write access is given to multiple process, need to keep track and combine them. Complexity increases.

2. Co-Operating Process
    - Information Sharing - Global Variable.
    - Computation Speed up - Merge Sort.
    - Modularity - Sub-Task.
    - Convenience - Single data, sharing with all.

3. Producer - Consumer [Handshaking]
    - Use Buffer
    - Bounded: Array
    - Unbounded: Memory that are dynamically allocated such as List
    - All output devices are Consumer. All input devices are Producer.

4. Remote
    - Network -> detected via IPV4: 32bit, IPV6: 128bit. Then server based id. Process ID is local to machine.<br>Now-a-days, nearly all programs are network oriented.
    - Unique Identification (URL)

5. Web server
    - Makes environment / platform ready.<br>
    - Server needs to host service that it wishes to provide.

6. Browsing
    - Via Terminal, Technical browsing.<br>
    - Browser provides internet service.
    - HTTPS, FTP are different service. Browser provides them.
    - If file is not fully downloaded, it cannot be viewed.
    <br>But, web page can be viewed - the portion that has been loaded.
    - `WPS` app provides browsing capability.

7. Socket = IP + Port Number
    - MAC (easy for machine)
    - IP (digit, low level)
    - DNS (name, easy for user, high level)

<br><h2><u>Lecture-05: 27th October, 2022</u></h2>

`Online class`

**🔥Chapter - 5: CPU Scheduling🔥**
- Basic Concepts
- CPU Scheduler
- Preemptive & Non-preemptive Scheduling
- Scheduling Criteria
- First Come, First Served (FCFS) Scheduling
- Shortest Job First (SJF)
- Round Robin

<br><h2><u>Lecture-06: 1st November, 2022</u></h2>

<b>🔥Chapter - 5: CPU Scheduling🔥</b>

1. Starvation
    - In Process Scheduling, some process may never get access to CPU. 

2. Aging
    - Priority is associated with each process.
    - Priority of waiting process will increase as time increases.
    So, they will get a chance.

3. Round Robin Scheduling
    - Time Quantum
    - n process after n iterations will get 1 chance
    - Waiting time is distributed, Response time better
    - If the only process in a queue needs 12 unit time & slot for each process is 2 unit, the process will be assigned 6 times. Though it is ok if task switching is negligible.

**⭐Advantage & Disadvantages⭐**

1. First Come First Service
    - Simplistic, no calculation required. All other methods need to manage, monitor, calculate.
2. Round Robin
    - After time limit is over, should the process be assigned again or is it done? Willingly replace or not?

<b>⭐Analytical Question:⭐</b> Define appropriate Priority Scheduling. Explain your answer with logic.
1. Foreground / User Process
    - Round Robin (Response important. In other methods, waiting time is more.)
2. Background Process
    - FCFS (All task are of similar level, length. Justify if other methods are used.)

**Question:** Do you agree or not?

<b>Multi-Level Queue</b>

- Process with different priority level is in different queue.

Among some System Process - Memory Allocation, Invalid Operation, Garbage Collection; priority of invalid operation is most, it is checked always. Garbage collection depends on situation.

<br><h2><u>Lecture-07: 3rd November, 2022</u></h2>

`Online Class`

<b>🔥Chapter - 5: CPU Scheduling🔥</b>

- Multi-Level Queue
- Multi-Level Feedback Queue
- Multiple-Processor Scheduling
- Real-Time CPU Scheduling
- Priority-based Scheduling
- Real Monotonic Scheduling

**🔥Chapter - 8: Deadlock🔥**
- Characterization
- Resource-Allocation Graph
- Methods for handling deadlock

<br><u><h2>Lecture-08: 8th November, 2022</u></h2>

**🔥Chapter - 8: Deadlock🔥**
- Deadlock - 4 characteristics
- Resource Allocation Graph - cycle, instance of resources

<br><u><h2>Lecture-09: 23rd November, 2022</u></h2>

**🔥Chapter - 8: Deadlock🔥**
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

**🔥Chapter - 8: Deadlock🔥**
- Deadlock Detection

<br><h2><u>Lecture-11: 4th December, 2022</u></h2>

**🔥Chapter - 8: Deadlock🔥**
- Deadlock Revised

**🔥Chapter - 9: Main Memory🔥**

<br><h2><u>Lecture-12: 5th December, 2022</u></h2>

**🔥Chapter - 9: Main Memory🔥**

<br><h2><u>Lecture-13: 7th December, 2022</u></h2>

**🔥Chapter - 9: Main Memory🔥**

<br><h2><u>Lecture-14: 11th December, 2022</u></h2>

`Online Class`

**🔥Chapter - 1: Introduction to OS🔥**

<br><h2><u>Lecture-15: 23rd December, 2022</u></h2>

`Online Class`

**🔥Chapter - 9: Main Memory🔥**
- Paging
- Structure of Page Table

<br><h2><u>Lecture-16: 27th December, 2022</u></h2>

`Online Class`

**🔥Chapter - 9: Main Memory🔥**
- Paging

**🔥Chapter - 10: Virtual Memory🔥**

<br><h2><u>Lecture-17: 29th December, 2022</u></h2>

`Online Class`

**🔥Chapter - 10: Virtual Memory🔥**

<br><h2><u>Lecture-18: 30th December, 2022</u></h2>

`Online Class`

**🔥Chapter - 10: Virtual Memory🔥**

<br><h2><u>Lecture-19: 31st December, 2022</u></h2>

`Online Class`

- [Term Test](Exam.md) Question Discussion

<br><h2><u>Lecture-20: 19th January, 2023</u></h2>

`Online Class`

**🔥Chapter - 2: Operating System Services🔥**
- System Call
- System Service
- Operating System Architecture (pros & cons)
    - Monolithic
    - Layered Approach

<br><h2><u>Lecture-21: 20th January, 2023</u></h2>

`Online Class`

Overview & Summary

**🔥Chapter - 10: Virtual Memory🔥**
- Translation Look-Aside Buffer (TLB)
- Second-chance Algorithm
- Thrashing 
