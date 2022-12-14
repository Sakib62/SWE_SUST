<h1 align="center">Numerical Analysis</h1>

<br>

**Book:** Numerical Methods for Engineers by Steven C. Chapra

**Site:** [MathForCollege](https://nm.mathforcollege.com)

<br><h2>=>Lecture-01: 29th August, 2022</h2>

- **Exact solution cannot always be extracted.** Need to obtain the most precise solution.
- **Numerical analysis deals with approximate solution.** How much error (Threshold value) will be accepted?

- **Why Numerical Methods?**
    - to solve problems that cannot be solved exactly
    - to solve problems that are intractable

- **How to solve an engineering problem?**
    - Problem Description
    - Mathematical Model (Converting the problem into mathematics for the computer to solve)
    - Solution of Mathematical model
    - Using the solution (Compare with existing solutions)

*My note: Need to revise following courses-> Calculus, Linear Algebra, Statistics*

<br><h2>=>Lecture-02: 31th August, 2022</h2>

**Why measure Errors?**
- to determine the accuracy of numerical results
- to develop stopping criteria for iterative algorithm

**Error**
- True Error, Relative True Error
- Approximate Error, Relative Approximate Error
- Absolute Relative Approximate Error (Used as stopping criteria)

**Mathematical Procedure**
- Nonlinear Equations
- Differentiation
- Simultaneous Linear Equations
- Curve Fitting (Interpolation, Regression)
- Integration
- Ordinary Differential Equations

**Advanced Mathematical Procedure**

- Partial Differential Equations
- Optimization
- Fast Fourier Transforms

*Software for lab*
- Matlab, Octave, Mathcad, Maple, Mathematica

<br><h2>=>Lecture-03: 5th September, 2022</h2>

<b>Root Finding Methods</b>
- Bisetion Method
- Method of False Position
- Newton Raphson's Method
- Fixed Point Iteration Method

Proofs, Maths, Step by step Solution<br>
If some digits after decimal point matches in consecutive iteration, terminate.

<br><b>Bisection Method</b>
- If a function ***f(x)*** is continuous between *a* and *b* and ***f(a).f(b) < 0*** (or ***f(a)*** and ***f(b)*** are of opposite sign), then there exist ***at least one root*** between *a* and *b*.

We can find only one root of ***f(x)*** within the interval ***[a, b]***.

[Bisection Method Root Finding Calculator](https://atozmath.com/CONM/Bisection.aspx)

Find the root of the following functions using bisection method:

1. *f(x) = x^3 - 2x^2 - 4 = 0* **(a = 2, b = 3)**
2. *f(x) = x^3 + x^2 - 1 = 0* **(a = 0, b = 1)**
3. *f(x) = x^2 + sin(x) - 1 = 0* **(a = null, b = null)**

<br><h2>=>Lecture-04: 14th September, 2022</h2>

**False Position Method**

- Equation Building
    - ( a, f(a) ) and ( b, f(b) ) are two points in the graph of given funciton f(x).
    - For two points (x1, y1) and (x2, y2), equation of straight line is: `(y-y1) / (y2-y1) = (x-x1) / (x2-x1)`
    - So, equation of straight line **ab** is: `(y-f(a)) / (f(b)-f(a)) = (x-a) / (b-a)`

<br>

- First Approximation
    - If Root point (x0, 0) is situated in this straight line, it will satisfy the equation.<br>Thus, `(0-f(a)) / (f(b)-f(a)) = (x0-a) / (b-a)`

    - So, First Approximate, `x0 = (af(b)-bf(a)) / (f(b)-f(a))`

<br>

- Condition Check
    - If f(x0) = 0, x0 is the Root.
    - Else 
        - If f(x0) * f(b) < 0, continue with ( x0, f(x0) ) and ( b, f(b) ) points
        - If f(x0) * f(a) < 0, continue with ( a, f(a) ) and ( x0, f(x0) ) points
        - Thus, Second Approximate value will be obtained.
        - Again Check Condition.
        - If same values after decimal points is re-obtained, it will be the root. Hence, stop iteration. 

<b>Find a real root of the equation: x^3 - 2x^2 - 4 = 0 (a=2, b=3)</b>

<br><hr><br>

**Newton Raphson Method**
- Starts with approximate value in order to find a value as close as root.

- `x1 = x0 + h`; *h is very small, tends to zero, can be positive or negative*
- `f(x1) = f(x0 + h)`
- Expansion by Taylor's series
    - `f(x0) + h f'(x0) + h^2/2! f''(x0) + .... = 0`

    - `f(x0) + hf'(x0) = 0 ` (Neglecting higher derivatives value, as they are very small)
    - `h = - (f(x0) / f'(x0)) ` (f(x0) != 0; if f(x0) = 0, then it is the root. No need of further calculation)

- So, First Approximate, `x1 = x0 - f(x0) / f'(x0)`
- **X0 can be calculated using Bisection or False Position Method**

<br>

**General Formula:** `Xn+1 = Xn - f(Xn) / f'(Xn); n = 0,1,2,3.....`

**Tasks**
- Proof, Geometric Expansion
- Find root using Newton Raphson Method: <b>x^3 - 2x^2 - 4 = 0 (a = 2, b = 3)</b>

<br><h2>=>Lecture-05: 19th September</h2>

- Interpolation
    - Newton's Forward & Backward Formula
- Lagrange's Interpolation Formula

<br><h2>=>Lecture-06: 17th October</h2>

- Numercal Differentiation
- Numerical Integration
    - Trapezoidal Rule
    - Simpson's 1/3 Rule
    - Simpson's 3/8 Rule


<br><h2>=>Lecture-07: 24th October</h2>

- ODE (Ordinary Differential Equation)
    - Euler Method
    - Runge Kutta Method (2nd Order)

<br>

- SLE (System of Linear Equation)
    - Gauss Jacobi Method
    - Gauss Seidel Method

<br><b>**Assignment Deadline: 8th November, 2022</b>
- Gaussian Elimination Method
- Gauss Jordan Method

<br><b>**Term Test 1: 9th November, 2022</b>

Root Finding Method
- Bisection
- False Position
- Newton-Raphson

<br><b>**Term Test 2: 16th November, 2022</b>

- ODE (Ordinary Differential Equation)
- SLE (System of Linear Equation)

<br><b>**Final: 16th January, 2023</b>