<h1 align="center">Theory of Computation</h1>
<h3 align="center"> <a href="https://drive.google.com/drive/u/0/folders/1xrvCjgRVIXaYLJ7Sjc6L1S_gI-sp-l_c" title="Drive Link of TOC"><ins>Drive Link</ins></a></h3>

<details><summary><h2>Book - Hopcroft</h2></summary>

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

<details><summary><h2>Lecture-01: 22nd August, 2022</h2> </summary>

1. What is Automata?
2. Deductive Proof
    - Prove that if x >= 4 then 2^x >= x^2
    - Prove that if x is the sum of squares of four positive integer numbers then 2^x = x^2

</details>

<details><summary><h2>Lecture-02: 12th September, 2022</h2></summary>

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
    ```
          
**Inductive Proof**

First a basis, then inductive steps (by incrementing basis)

<details><summary><b>If x>=4 then 2^x>=x*x</b></summary>

For basis: x = 4

I.S: 2^(x+1) >= (x+1)*(x+1)<br>
    - In inductive step: If H then C where H is 2^x >= x * x and C is 2^(x+1) >= (x+1) * (x+1)<br>
We assume given statement is true.

```
=> 2^x . 2 >= (x+1)^2
=> x^2 . 2 >= (x+1)^2
=> 2. x^2 >= x^2 + 2x + 1
=> x^2 >= 2x + 1
=> x >= 2 + 1/x
```

If x==4, `4 >= 2 + 1/4 => 4 >= 2.25`

If x > 4, 1/x gets smaller<br>
So, L.H.S is always greater than R.H.S

**So, hypothesis holds!**
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

<details><summary><h2>Lecture-03: 19th September, 2022</summary>

</details>

<details><summary><h2>Lecture-04: 26th September, 2022</summary>

</details>

<details><summary><h2>Lecture-05: 17th October, 2022</summary>

**Regular Expression**

It is case sensitive.<br>To search specific string in another string.

**/x/ Forward Slash**
>Need to match the content inside forward slash only ONCE.

**[] Disjunction**
>[A-Za-z0-9] - in a range.. Here, any alpha numeric is ok.<br>
>Only single digit is used in range. [1-100] is wrong.

<details><summary><b>Caret (^) is used in 3 places.</b></summary>

1. Caret is first symbol in a range. [^a-z] -> a-z is negated.<br>Anything other than [a-z] is ok. [^Ss] means neither S nor s.

2. Caret is just a character. /a^b/

3. Caret is first symbol in forward slash. /^The/ -> Sring needs to be started with The.<br>
   > The USA has the... Here /^The/ is ok. 
</details>
<details><summary><b>?</b></summary>

> 0 or 1 instance of previous character.<br>Colou?r -> Colour or Color both ok.<br>To check ? -> \?? (Backword slash as a escape character, Second ? checks whether first ? is present.)<br>
\ \ \ ? ? -> Either \ or \? (As ? may present 0 or 1 time.)
<br>\ \ \ ? ? ? -> Invalid.
<br> [^ \ \ \ ? ?] -> ? doesn't work in disjunction. Individual character is chekced. 
</details>

**\***
> Zero or more occurrences of immediate previous character.
<br>/[0-9][0-9]*/ -> [0, infinity) Can be written by [0-9]+ also.
<br>baa* -> ba, baa, baaa,...

**+**
>One or more occurrences of previous character.<br>
ba+ -> ba, baa..

**Wildcard(.)**
> / . / matches any single character (except a carriage return.)
<br> /beg.n/ -> Any character between beg and n.<br> beg'n, begun ok. begn not ok.

<details><summary>Bonus</summary>

```
The wildcard is often used together with kleene * to mean 
any string of characters.

/the.*the/ -> the us has the most oil (Here, from 1st 'the' to 2nd 'the' is chekced and is ok. )

Also /x/ means x must be present exactly.
```
</details>

<details><summary><b>Anchor</b></summary>

> \$, ^
<br>To put RE to particular places in string.
<br>\$ matches the end of a line.
<br>/end$/ -> This end is not the end (Last end is matched)
<br><br> ␣*\$ -> str.trim() where ␣ indicates space
<br> ␣\$ -> for matching a space at the end of a line.
<br><br> /^The dog\\.\$/ ->Here `\` before `.` means `.` is a character<br>^ means the string has to be in the first place of another string<br>$ means a line has to end with this string.
<br>So this RE will only match `a line that contains the phrase 'The dog.'`
</details>

`WORD = any sequence of digits, underscore or letters.`

<details><summary><b>Boundary</b></summary>

/the/ will match `other` caue it contains `the`<br>
But, /\bthe\b/ will only match the.
<br><br>For /\b99\b/

- There are 99 bottles. (ok)
- There are 299 cup. (Not ok)
- It cost $99 only. (ok - cause dollar is not digit, underscore, letter.)
</details>

</details>

<details><summary><h2>Lecture-06: xth October, 2022</summary>

</details>