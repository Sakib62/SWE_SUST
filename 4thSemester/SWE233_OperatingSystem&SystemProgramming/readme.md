<h1 align="center">Operating System and System Programming</h1>
<h3 align="center"> <a href="https://drive.google.com/drive/u/0/folders/1ipS8U50KywocfKG1-dZfjWogO1PYDndL" title="Drive Link of OS"><ins>Drive Link</ins></a> </h3>

<h2>Resource:</h2>

[fba13](https://www.youtube.com/watch?v=tBVWKGBAeQ8&list=PLJW6cU20q-SNCeRTbz3gOO6MMJb5C3tNO)

<details><summary><h2>Lecture-01: 22nd August, 2022</h2></summary>


</details>

<details><summary><h2>Lecture-02: 30th August, 2022</h2></summary>


</details>

<details><summary><h2>Lecture-03: 5th September, 2022</h2></summary>

Process

</details>

<details><summary><h2>Lecture-04: 11th October, 2022</h2></summary>

Process

</details>

<details><summary><h2>Lecture-05: 18th October, 2022</h2></summary>


</details>

<h2>Lecture-06: 20th October, 2022</h2>

Online class

<h2>Lecture-07: 25th October, 2022</h2>

<h2>Lecture-08: 27th October, 2022</h2>

Online class

<details><summary><h2>Lecture-09: 1st November, 2022</h2></summary>

<b>Chapter 5: CPU Scheduling</b>

<b>Priority Scheduling</b>

Shutdown
- Command line/gui/ctrl+alt+f4
- Pull out cable
- Press Power Button (works in micro-processor level)

Aging:

- Waiting process will get chance, as their priority increases as time increases.

<b>Example of Priority Scheduling</b>

<b>Round Robin</b>
- Time Quantum
- n process after n iterations will get 1 chance
- Waiting time is distributed, Response time better
- If the only process in a queue needs 12 unit time & slot for each process is 2 unit, the process will be assigned 6 times. Though it is ok if task switching is negligible.

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

Garbage collection depends on situation.

Invalid operation is checked always.

So these are in different queue. If in same queue, different priority.

<b>NEXT CLASS: QUIZ on PROCESS. 20 marks</b>

</details>