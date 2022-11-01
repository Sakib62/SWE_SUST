<h1 align="center"> Algorithm Design and Analysis </h1>

<h3 align="center"> <a href="https://drive.google.com/drive/u/0/folders/1ZwZHAAirbBEvp0mxAs3urO2tOawbSw1N" title="Drive Link of Algo">Drive Link</a></h3>

[DP Resource](https://bit.ly/dpseriestuf)

<details><summary><h2>Syllabus</h2></summary>
<blockquote> <p>
Sieve - Bitwise, Segmented, Linear<br>
Divisor - Count, Sum<br>
Phi<br>
Modular Inverse - with Power, with Ext. Euclid<br>
CRT - Ext. Euclid

Floyd Warshall<br>
Bellman Ford<br>
Heapsort - Heap<br>
Counting Sort, Radix Sort, Bucket Sort<br>
Order Statistics<br>
Hash Table<br>
Binary Search Tree<br>
Balance Binary Search Tree - Treap / AVL Tree

DP - Matrix Chain Multiplication, Knapsack, CoinChange<br>
Greedy - Task Scheduling<br>
Max Flow - Ford Fulkerson

String Matching - KMP, Rabin Karp (Hashing)<br>
Suffix Array<br>
Strongly Connected Component

FFT* (probably)

Quicksort*, DSU*, MST*, Dijkstra*, DFS*, BFS* (covered in CP course)
</p></blockquote>
</details>

<details><summary><h2>Lecture-01: 23th August, 2022</h2></summary>

1. Sieve of Eratosthenes
2. Linear Sieve
</details>

<details><summary><h2>Lecture-02: 28th August, 2022</h2></summary>

1. Bitwise Operation
2. Bitwise Sieve
</details>

<details><summary><h2>Lecture-03: 30th August, 2022</h2></summary>

1. Segmented Sieve
</details>

<details><summary><h2>Lecture-04: 4th September, 2022</h2></summary>

1. Euler phi
1. Count of Divisor
2. Sum of Divisor
3. Prime in cube root complexity, N = P * Q * R, Miler Rabin
</details>

<details><summary><h2>Lecture-05: 6th September, 2022</h2></summary>

1. BigMod / Modular Exponentiation
2. Extended Euclid
3. Modular Multiplicative Inverse
4. Fermat's Little Theorem

https://cp-algorithms.com/algebra/extended-euclid-algorithm.html
</details>

<details><summary><h2>Lecture-06: 11th September, 2022</h2></summary>

1. Shortest Path 
2. Floyd Warshall
</details>

<details><summary><h2>Lecture-07: 18th September, 2022</h2></summary>

1. Bellman Ford
2. Chinese Remainder Theorem
</details>

<details><summary><h2>Lecture-08: 20th September, 2022</h2></summary>

1. Chinese Remainder Theorem (Code of Weak Form + Strong Form discussion)
</details>

<details><summary><h2>Lecture-09: 25th September, 2022</h2></summary>

1. Heap Sort (Heapify & Sorting)
</details>

<details><summary><h2>Lecture-10: 16th October, 2022</h2></summary>

1. Counting Sort
</details>

<details><summary><h2>Lecture-11: 18th October, 2022</h2></summary>

1. Some primary info about Git operation.
2. Pull Request, Fork, Collaborations.
3. Sublime Merge

</details>

<details><summary><h2>Lecture-12: 23th October, 2022</h2></summary>

1. Radix Sort
2. Bucket sort

</details>

<details><summary><h2>Term Test-1: 26th October, 2022</h2></summary>

*Pseudo Code/Algorithm/Code*

- Sieve & variations
- Extended Euclid Algorithm
- Modular Multiplicative Inverse
- Chinese Remainder Theorem
- Bellman Ford Algorithm
- Floyd Warshall Algorithm

Question:

1. State the formal definition of CRT.
2. Prove the existence of Modular Inverse of a number A with respect to M.
3. What do you understand by 'Path Relaxation'?
4. Can you improvise the following code to run faster? Explain your answer with complexity analysis.<br>
```cpp
void SieveOfEratosthenes (int n)
{
    bool prime[n + 1];
    memset(prime, true, sizeof(prime));

    for (int p = 2; p * p <= n; p++) {
        if (prime[p] == true) {
            for (int i = p * p; i <= n; i += p) 
                prime[i] = false;
        }
    }
    for (int p = 2; p <= n; p++)
        if (prime[p])
            cout << p << " ";
}
```
5. Write down each step for the 'Floyd-Warshall Algorithm' on the following graph. **Start from node a.**<br>
Directed Edges with weight:<br>
(a, g) = 7, (a, b) = 4, (a, h) = 4<br>
(b, f) = 6, (b, g) = 8, (b, h) = 1<br>
(g, b) = 4, (g, f) = 7

</details>

<h2>Lecture-13: 30th October, 2022</h2>

ALgo, Complexity Analysis

1. Merge Sort 
2. Quick Sort