<h1 align="center">Numerical Analysis</h1>

<h3 align="center"> 
  <a href="https://drive.google.com/drive/folders/1H0gzCqMc6RTRGk0Y4Bt01B_fKU_Ohs8p" title="Drive Link of NA"> <ins>Drive Link</ins> </a>
  &nbsp;&nbsp; &nbsp;&nbsp;
  <a href="https://nm.mathforcollege.com/" title="Website"><ins>Online</ins></a>
</h3> 

<br>

***Book: Numerical Methods for Engineers by Steven C. Chapra***

## Lecture-01: 29th August, 2022

Exact solution cannot always be extracted. We need to be as precise as we can.

Numerical analysis deals with approximate aolution. How much error(threshold value) will be accepted?

**Why use Numerical Methods?**
- to solve problems that cannot be solved exactly
- to solve problems that are intractable

**How to solve an engineering problem?**<br>
Problem Description->Mathematical Model->Solution of Mathematical model->Using the solution

*(~Need to follow this for Research/Journal~)*

**Mathematical Model:** Converting the problem into mathematics so that computer can help solve this problem.

**Using the solution:** Compare with existing solutions. 

*(~My note: Need to revise following course-> Calculus, Linear Algebra, Statistics~)*

<br>
<br>

## Lecture-02: 31th August, 2022

**Why measure errors?**
- to determine the accuracy of numerical results
- to develop stopping criteria for iterative algorithm

**Error**
- True error
- Relative true error
- Approximate error
- Relative approximate error
- Absolute relative approximate error (Used as a stopping criteria)
    - If |∈a|<=∈s where ∈s is a pre-specified tolerance, then no further iterations are necessary and the process is stopped.

**Mathematical Procedure**
- Nonlinear Equations
- Differentiation
- Simultaneous Linear Equations
- Curve Fitting
    - Interpolation
    - Regression
- Integration
- Ordinary Differential Equations

**Advanced Mathematical Procedure**
- Partial Differential Equations
- Optimization
- Fast Fourier Transforms

*Software that can be used:*
- Matlab
- Octave(free, light)
- Mathcad
- Maple
- Mathematica

<br>
<br>

## Lecture-03: 5th September, 2022

Through Numerical Analysis
- we find an approximate value
- minimize error
- theoretically stop iteration after fulfiling some criteria

**Root Finding Methods**

f(x) = x^3 - 6x^2 + 11x - 6 = 0

f(1) = 0, f(2) = 0, f(3) = 0 (~Points where roots are found, are Zero Funciton~)

We do not need numerical analysis here because we have found the exact solutions.

*Some root finding methods are:*
- Bisetion Method
- Method of False Position
- Newton Raphson's Method
- Fixed Point Iteration Method

(~Need to learn proof of these methods~)<br>
(~Math using calculator. Solution size is large. Step By Step by following book. If some digits after decimal point matches in consecutive iteration, terminate.~)

**Bisection Method**

If a function ***f(x)*** is continuous between *a* and *b* and ***f(a).f(b) < 0*** (or ***f(a)*** and ***f(b)*** are of opposite sign), then there exist ***at least one root*** between *a* and *b*.

We can find only one root of ***f(x)*** within the interval ***[a, b]***.

[Bisection Method Root Finding Calculator](https://atozmath.com/CONM/Bisection.aspx)

Find the root of the following functions using bisection method:

1. ***f(x) = x^3 - 2x^2 - 4 = 0; a = 2, b = 3***
2. ***f(x) = x^3 + x^2 - 1 = 0; a = 0, b = 1***
3. ***f(x) = x^2 + sin(x) - 1 = 0; a = null, b = null***

<br>
<br>
