<h1 align="center">Theory of Computation</h1>
<h3 align="center"> <a href="https://drive.google.com/drive/u/0/folders/1xrvCjgRVIXaYLJ7Sjc6L1S_gI-sp-l_c" title="Drive Link of TOC"><ins>Drive Link</ins></a></h3>

<details>
<summary> <h2>Book - Hopcroft</h2> </summary>

**Chapter**
  1. Automata: The Methods and the Madness
  2. Finite Automata
  3. Regular Expressions and Languages
  4. Poperties of Regular Languages (~*Sir might teach this chapter*~)
  5. Context-Free Grammars and Languages (~*Noam Chomsky*~)
  6. PushDown Automata (~*tough?*~)
  7. ~Properties of Context-Free Languages~
  8. Introduction to Turing Machines (~*complex?*~)
  9. Undecidability
  10. Intractable Problems (~*if 9, then 10 also included*~)
  11. ~Additional Classes of Problems~

**Evaluation**
- Quiz
- Term Test
- Class Performance
- Attendance

</details>

<details>
<summary> <h2>Lecture-01: 22nd August, 2022</h2> </summary>

1. What is Automata?
2. Deductive Proof
    - Prove that if x >= 4 then 2^x >= x^2
    - Prove that if x is the sum of squares of four positive integer numbers then 2^x = x^2

</details>

<details>
<summary><h2>Lecture-02: 12th September, 2022</h2></summary>

**Proof about Sets**

**Proof by contradiction**
- Whether a number is irrational or not?
- Initially assume, *If H then C*.
    - Then work with *If not H then C.* If this is not true, then initial assumption is true.

**Proof by counter example**
- All odd numbers are prime (Not all)
- <details> <summary><b>Prove: There is no pair of integer a and b such that a mod b = b mod a (a!=b)</b></summary>
     
     ```
        ### a > b
            a mod b = c = [0, b-1]
            
            b mod a = b
            
            So, b mod a > a mod b
            
        ### a < b
            a mod b = a
            
            b mod a = c = [0, a-1]
            
            So, a mod b > b mod a
            
        ### a == b (Need to cover whole domain)
            a mod b = a mod a = 0
            b mod a = 0
            
            So, a mod b == b mod a
            
        So, If a!=b then there is no pair of integer a and b such that a mod b = b mod a
      
      
**Inductive Proof**

First a basis, then inductive steps(by incrementing basis)

<details><summary><b>If x>=4 then 2^x>=x*x</b></summary>

For basis: x = 4

I.S: 2^(x+1) >= (x+1)*(x+1)
    - In inductive step: If H then C where H is 2^x>=x*x and C is 2^(x+1) >= (x+1)*(x+1)
    - We assume given statement is true.

```
=> 2^x . 2 >= (x+1)^2
=> x^2 . 2 >= (x+1)^2
=> 2. x^2 >= x^2 + 2x + 1
=> x^2 >= 2x + 1
=> x >= 2 + 1/x
```

If x==4, 4 >= 2 + 1/4 => 4 >= 2.25

If x > 4, 1/x gets smaller
So, R.H.S is always greater than L.H.S

So, hypothesis holds!
<br>
</details>
        
<details><summary><b>For n >= 0, summation of i^2(i from 0 to n) = n * (n+1) * (2n+1) / 6</b></summary>

Basis Step: n = 0

I.S: summaiton of i^2(i from 0 to n+1) = 

```
(n+1) *  (n+2) * (2n+3) / 6 = (2n^3+9n^2+13n+6)/6

=> summation of i^2 from 0 to n + (n+1)^2 = (2n^3+9n^2+13n+6)/6

=>  n * (n+1) * (2n+1) / 6 + (n+1)^2 = (2n^3+9n^2+13n+6)/6
```

</details>

</details>

<details>
<summary><h2>Lecture-03: 19th September, 2022</summary>

</details>
