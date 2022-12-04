<h1 align="center"> Algorithm Design and Analysis </h1>

<h3 align="center"> <a href="https://drive.google.com/drive/u/0/folders/1ZwZHAAirbBEvp0mxAs3urO2tOawbSw1N" title="Drive Link of Algo">Drive Link</a></h3>

[DP Resource](https://bit.ly/dpseriestuf)

<details><summary><h2>Syllabus</h2></summary>

:white_check_mark: Sieve - Bitwise, Segmented, Linear<br>
:white_check_mark: Divisor - Count, Sum<br>
:white_check_mark: Phi<br>
:white_check_mark: Modular Inverse - with Power, with Ext. euclid<br>
:white_check_mark: CRT - Ext. Euclid

:white_check_mark: Floyd Warshall<br>
:white_check_mark: Bellman Ford<br>
:white_check_mark: Heapsort - Heap<br>
:white_check_mark: Counting Sort, Radix Sort, Bucket Sort<br>
Order Statistics<br>
Hash Table<br>
Binary Search Tree<br>
Balance Binary Search Tree - Treap / AVL Tree

:white_check_mark: DP: Top Down(Recursive), Bottom Up(Iterative), 0-1 Knapsack<br>
:white_check_mark: Longest Common Subsequence<br>
Matrix Chain Multiplication, CoinChange<br>
Greedy - Task Scheduling<br>

:white_check_mark: Max Flow - Ford Fulkerson

:white_check_mark: String Matching - KMP, Rabin Karp (Hashing)<br>
Suffix Array<br>
Strongly Connected Component

FFT* (probably)

**Covered in Cp Course**<br>
- [x] Quicksort
- [x] DSU
- [x] MST
- [x] Dijkstra
- [x] DFS 
- [x] BFS

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

<h3><b>Counting Sort</b></h3>

1. Not comparison based.<br>Stable Sorting Algorithm -> Important if number is associated with something.<br><br>
Stability of sorting algorithm simply means that<br> the relative ordering of elements with same keys will remain same before & after the sorting.<br><br>
1. Particular Range
2. Initialize count array for elements
3. Frequency table (index sorted, so no comparison)
4. Cumulative sum //*Can find sorted array from this part too.*
5. From reverse to ensure stable sort
    ```cpp
    for(int i = n-1; i >= 0; i--) {
        output[count[arr[i]] - 1] = arr[i]
        count[arr[i]]--; //If same number repeats, order will be same
    }
    ```
6. Complexity: O(n+k), k is range for cumulative sum

    <details><summary>Code:</summary>

    ```cpp
    //Bismillahir Rahman-ir Rahim
    #include <bits/stdc++.h>
    using namespace std;

    void countSort(int *a, int n) {
        int mx = *max_element(a, a+n); //to determine range of freq array
        int freq[mx + 1] = {0}, ans[n];

        for(int j = 0; j < n; j++) { //frequency array
            freq[a[j]]++;
        }
        for(int j = 1; j < mx + 1; j++) { //prefix sum
            freq[j]+=freq[j-1]; //can complete sorting in this point though won't be stable
        }
        //from last to make stable sorting
        for(int i = n - 1; i >= 0; i--) {
            ans[freq[a[i]] - 1] = a[i];//-1 to fit in 0 based indexing. a[i] is freq[a[i]]th element if sorted
            freq[a[i]]--;//already placed this one, hence decrement
        }
        //copy into original array
        for(int i = 0; i < n; i++) {
            a[i] = ans[i];
        }
    }

    void solve() {
        int n;
        cin >> n;
        int a[n];
        for(int i = 0; i < n; i++) {
            cin >> a[i];
        }
        countSort(a, n);
        for(int i = 0; i < n; i++) {
            cout << a[i] << " ";
        }
        cout << "\n";
    }

    int main() {
        ios_base::sync_with_stdio(false); cin.tie(0); int testCase = 1;
        //cin >> testCase;
        while(testCase--) {
            solve();
        }
    }
    ```
    </details>
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

<img src="assets\TT1.jpg" width="60%" height="10%">

</details>

<h2>Lecture-13: 30th October, 2022</h2>

ALgo, Complexity Analysis

1. Merge Sort 
2. Quick Sort

<details><summary><h2>Lecture-14: 8th November, 2022</h2></summary>

<details><summary><b>String Hashing</b></summary>

- h(k1) = h(k2) [k1!=k2]<br>
- if this condition is violated, collision occurs.
- Goal is to reduce collision probability.
</details>

<details><summary><b>Ways to mitigate collision</b></summary>

1. **Hashing With Chain**<br>
    For each index, a linked list

2. **Linear Probing**<br>
    Put in immediate next empty index. Worst case of insertion is O(n).

3. **Quadratic Probing**<br>
    Put in index derived from formula. Worst case improved.
</details>

**How to retrieve?**<br>
**Why prime is used to mod?**

<details><summary><b>Load Factor (alpha)</b></summary>

- At most how many value will be mapped at a index?
- N/K -> Assuming keys are random.
- So, O(1 + alpha)
</details>

Resource for hash table:

[Programiz](https://www.programiz.com/dsa/hash-table)<br>[Hackerearth](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)
<br>[maximal](https://datastructures.maximal.io/hash-tables/)
<br>[medium](https://medium.com/basecs/hashing-out-hash-functions-ea5dd8beb4dd)

</details>

<h2>Lecture-15: 13th November, 2022</h2>

Hashing proof

Universal hashing function

random indicator

<h2>Lecture-16: 15th November, 2022</h2>

Ford Fulkerson for MaxFlow

<h2>Lecture-17: 22th November, 2022</h2>

0-1 knapsack

Top Down & Bottom Up approach

Next: Coin Change, LCS, 

<h2>Lecture-18: 4th December, 2022</h2>

1. Length of **LCS - Longest Common Subsequence** with Top-Down(Recursive) & Bottom-Up(Iterative) Approach. 

2. the subsequence itself.

<h2>Term Test-2: 8th December, 2022</h2>

Thursday

**Syllabus**: 
1. Sorting
    - Stable Sort(Counting, Bucket, Radix)
    - Heap Sort, Merge Sort, Quick Sort
2. Ford Fulkerson
3. DP (0-1 knapsack, LCS)