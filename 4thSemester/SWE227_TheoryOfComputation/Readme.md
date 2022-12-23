<h1 align="center">Theory of Computation</h1>

**Youtube Playlist**

[Neso Academy](https://www.youtube.com/playlist?list=PLBlnK6fEyqRgp46KUv4ZY69yXmpwKOIev)
, [Lecturelia](https://www.youtube.com/playlist?list=PLncy2sD7w4YqBniaSEkOtzcZa3UNtWpMF)
, [Anisul Islam](https://www.youtube.com/playlist?list=PLgH5QX0i9K3qw5pu16QgnKNj91Rnjoyd0)
, [Lydia](https://www.youtube.com/playlist?list=PLhqug0UEsC-IDomfNsn8e3neoy34o8oye)

**Book** - [Hopcroft - Introduction to Automata Theory](Books/Hopcraft-Introduction_to_Automata_Theory.pdf)

<br><h2><u>Lecture-01: 22nd August, 2022</u></h2>

1. What is Automata?
2. Deductive Proof
    - Prove that if `x >= 4`, then `2^x >= x^2`
    - Prove that if x is the sum of squares of four positive integer numbers, then `2^x >= x^2`

<br><h2><u>Lecture-02: 12th September, 2022</u></h2>

- Proof about Sets
- Proof by Contradiction
    - Initially assume, If H then C.
    - Then work with If not H then C. 
    - If this is not true, then initial assumption is true.
    - Application: Proof of whether a number is irrational or not?
- Proof by Counter Example

<b>Prove: There is no pair of integer a and b such that a mod b = b mod a (a!=b)</b>
- If a > b, `b mod a` > `a mod b`
- If a > b, `a mod b` > `b mod a`
- If a = b, `a mod b` = `b mod a`
- So, If `a != b`, then there is no pair of integer a and b such that `a mod b` = `b mod a`

<br><hr><br>

**Inductive Proof**
- First a basis
- Then inductive steps (by incrementing basis)

<b>Prove:</b> If `x >= 4` then `2^x >= x * x`
- For basis: x = 4
- Inductive Step: `2^(x+1)` >= `(x+1) * (x+1)`

>In inductive step, If H then C. <br>
Here H is `2^x` >= `x * x` and C is `2^(x+1)` >= `(x+1) * (x+1)`

**We assume given statement is true**
- `2^(x+1)` >= `(x+1) * (x+1)`
- `2^x . 2` >= `(x+1)^2`
- `x^2 . 2` >= `(x+1)^2` [Given, `2^x` >= `x^2`]
- `2. x^2` >= `x^2 + 2x + 1`
- `x^2` >= `2x + 1`
- `x` >= `2 + 1/x`

**Conclusion**
- If x = 4, **4 >= 2 + 1/4** => **4 > 2.25**
- For x > 4, 1 / x gets smaller
- So, L.H.S. > R.H.S
- If `x >= 4` then `2^x >= x * x` [Proved]
- **So, hypothesis holds**

<br>
        
<b>Prove: For n >= 0, summation of i^2(i from 1 to n) = n * (n+1) * (2n+1) / 6</b>

<br><h2><u>Lecture-03: 19th September, 2022</u></h2>

- Finite State Machine
- Deterministic Finite Automata (DFA)

<br><h2><u>Lecture-04: 26th September, 2022</u></h2>
- Non-Deterministic Finite Automata (NFA)
- NFA to DFA conversion

<br><h2><u>Lecture-05: 17th October, 2022</u></h2>

- **Regular Expression**
    - It is case sensitive.
    - To search specific string in another string.

<br>

- **/x/ Forward Slash**
    - Need to match the content inside forward slash only ONCE.

<br>

- **[] Disjunction**
    - [A-Za-z0-9] - in a range. Here, any alpha numeric is ok.

    - Only single digit is used in range. [1-100] is wrong.

<br>

- <b>Caret (^) is used in 3 places.</b>
    1. Caret is first symbol in a range. [^a-z] -> a-z is negated.<br>Anything other than [a-z] is ok. [^Ss] means neither S nor s.

    2. Caret is just a character. /a^b/

    3. Caret is first symbol in forward slash. /^The/ -> Sring needs to be started with The.<br>
    The USA has the... Here /^The/ is ok. 

<br>

- <b>?</b>
    - 0 or 1 instance of previous character.
    - `Colou?r` -> Colour or Color both ok.

    - `To check ? itself` -> \\?? (Backword slash as a escape character, Second ? checks whether first ? is present.)
    - \ \ \ ? ? -> Either \ or \? (As ? may present 0 or 1 time.)
    - \ \ \ ? ? ? -> Invalid.
    - [^ \ \ \ ? ?] -> ? doesn't work in disjunction. Individual character is chekced. 

- **Kleene \***
    - Zero or more occurrences of immediate previous character.
    - /[0-9][0-9]*/ -> [0, infinity) Can be written by [0-9]+ also.
    - baa* -> ba, baa, baaa,...

- **+**
    - One or more occurrences of previous character.<br>
    - ba+ -> ba, baa..

- **Wildcard(.)**
    - / . / matches any single character (except a carriage return.)
    - /beg.n/ -> Any character between beg and n.
    - beg'n, begun ok. begn not ok.

    - **The wildcard is often used together with kleene * to mean any string of characters.**

    - /the.*the/ -> the us has the most oil (Here, from 1st 'the' to 2nd 'the' is chekced and is ok. )

    - **/x/ means x must be present exactly.**


- <b>Anchor (\$, ^)</b>
    - To put RE at particular places in string.
    - `$` matches the end of a line.
    - `/end$/` -> "This end is not the `end`" (Here, last end is matched)

    - `␣*`\$ means str.trim() where `␣` indicates space

    - `␣$` -> for matching a space at the end of a line.

    - /^The dog\\.\$/ 
        - Here `\` before `.` means `.` is a character
        - `^` means the string has to be in the first place of another string
        - `$` means a line has to end with this string.
        - So this RE will only match `a line that contains the phrase 'The dog.'`

`WORD = any sequence of digits, underscore or letters.`

- <b>Boundary</b>
    - /the/ will match `other` caue it contains `the`
    - But, /\bthe\b/ will only match the.
    - For /\b99\b/
        - There are 99 bottles. (ok)
        - There are 299 cup. (Not ok)
        - It cost $99 only. (ok - cause dollar is not digit, underscore, letter.)

<br><h2><u>Lecture-06: 24th October, 2022</u></h2>
- Regular Language
- Pumping Lemma


<br><h2><u>Lecture-07: 31th October, 2022</u></h2>

- Context Free Languages

<b>Grammar</b>
- V = set of Non-Terminal Symbol
- T = set of Terminal Symbol
- S = Start Symbol
- P = Production Rule
- G = ({S, A, B}, {a, b}, S, {S -> AB, A -> a, B -> b}) where
    - {S, A, B} is V
    - {a, b} is T
    - S is S
    - {S -> AB, A -> a, B -> b} is P

**Example**

- **S -> AB**
- **A -> a | aA** (A gives a or aA)
- **B -> b | phi** (B gives b or nothing)

G = ({S, A, B}, {a, b}, S, {S -> AB, A -> a | aA, B -> b | phi})

**Non-Terminal can give both Terminal & Non-Terminal.**

*Finite State Machine express Regular Language*<br>
*PushDown Automata express Context Free Grammar*

<br><hr><br>

<b>Chomsky Normal Form</b>
- A -> a (Non-Terminal to Terminal)
- A -> BC (Non-Terminal to maximum 2 Non-Terminal)

In case of more than 2 Non-Terminal:
- If A -> BCD
    - A -> XD
    - X -> BC

<b>Convert CFG to CNF</b>

1. If start symbol S occurs on some right side, create a new symbol S' and production S -> S'
2. Remove Null Productions
3. Remove Unit Productions
4. Replace each Productions<br>
A -> B1....Bn where n > 2 with A -> B1C, C -> B2....Bn and repeat until n<=2

5. If A -> aB (NT -> T + NT)<br>
Then, A -> XB (NT -> NT + NT)<br>
and X -> a (NT -> T)

<br><h2><u>Lecture-08: 7th November, 2022</u></h2>
- Conversion of Context Free Grammar to Chomsky Normal Form with example.

<br><h2><u>Lecture-09: 7th December, 2022</u></h2>
- PushDown Automata
- Turing Machine