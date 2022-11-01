<h1 align="center">Numerical Analysis</h1>

<h3 align="center"> 
  <a href="https://drive.google.com/drive/folders/1H0gzCqMc6RTRGk0Y4Bt01B_fKU_Ohs8p" title="Drive Link of NA"> <ins>Drive Link</ins> </a>
  &nbsp;&nbsp; &nbsp;&nbsp;
  <a href="https://nm.mathforcollege.com/" title="Website"><ins>Online</ins></a>
</h3> 

<br>

***Book: Numerical Methods for Engineers by Steven C. Chapra***

<details>
<summary><h2>Lecture-01: 29th August, 2022</h2></summary>

Exact solution cannot always be extracted. We need to be as precise as we can.<br>
Numerical analysis deals with approximate aolution. How much error(threshold value) will be accepted?

**Why use Numerical Methods?**
>- to solve problems that cannot be solved exactly
>- to solve problems that are intractable

**How to solve an engineering problem?**<br>
>Problem Description->Mathematical Model->Solution of Mathematical model->Using the solution

**Mathematical Model:** 
>Converting the problem into mathematics so that computer can help solve this problem.<br>

**Using the solution:** 
>Compare with existing solutions. 

*My note: Need to revise following courses-> Calculus, Linear Algebra, Statistics*

</details>

<details>
<summary><h2>Lecture-02: 31th August, 2022</h2></summary>

<details>
<summary><b>Why measure errors?</b></summary>

- to determine the accuracy of numerical results
- to develop stopping criteria for iterative algorithm
</details>

<details>
<summary><b>Error</b></summary>

- True error
- Relative true error
- Approximate error
- Relative approximate error
- Absolute relative approximate error (Used as a stopping criteria)
    - If |∈a|<=∈s where ∈s is a pre-specified tolerance, then no further iterations are necessary and the process is stopped.

</details>

<details>
<summary><b>Mathematical Procedure</b></summary>

- Nonlinear Equations
- Differentiation
- Simultaneous Linear Equations
- Curve Fitting
    - Interpolation
    - Regression
- Integration
- Ordinary Differential Equations
</details>

<details>
<summary><b>Advanced Mathematical Procedure</b></summary>

- Partial Differential Equations
- Optimization
- Fast Fourier Transforms
</details>

<details>
<summary><i>Software that can be used:</i></summary>

- Matlab
- Octave(free, light)
- Mathcad
- Maple
- Mathematica
</details>

</details>

<details>
<summary><h2>Lecture-03: 5th September, 2022</h2></summary>

<details><summary><b>Through Numerical Analysis, we can</b></summary>

>- find an approximate value
>- minimize error
>- theoretically stop iteration after fulfiling some criteria
</details>

```
f(x) = x^3 - 6x^2 + 11x - 6 = 0
f(1) = 0, f(2) = 0, f(3) = 0 //Points where roots are found, are Zero Funciton
We do not need numerical analysis here because we have found the exact solutions.
```

<details><summary><b>Root Finding Methods</b></summary>

- Bisetion Method
- Method of False Position
- Newton Raphson's Method
- Fixed Point Iteration Method
</details>

>Review proof of these methods. Math using calculator. Solution size is large. Step By Step following book.<br>
>If some digits after decimal point matches in consecutive iteration, terminate.

<details><summary><b>Bisection Method</b></summary>

<br>

>If a function ***f(x)*** is continuous between *a* and *b* and ***f(a).f(b) < 0*** (or ***f(a)*** and ***f(b)*** are of opposite sign), then there exist ***at least one root*** between *a* and *b*.

We can find only one root of ***f(x)*** within the interval ***[a, b]***.

[Bisection Method Root Finding Calculator](https://atozmath.com/CONM/Bisection.aspx)

Find the root of the following functions using bisection method:

1. ***f(x) = x^3 - 2x^2 - 4 = 0; a = 2, b = 3***
2. ***f(x) = x^3 + x^2 - 1 = 0; a = 0, b = 1***
3. ***f(x) = x^2 + sin(x) - 1 = 0; a = null, b = null***
</details>

</details>

<details>
<summary><h2>Lecture-04: 14th September, 2022</h2></summary>

**🎈False Position Method**

In the graph of a given funciton f(x), point1 (a, f(a)) & point2 (b, f(b)) makes a straight line.

<details>
<summary><b>Given two points, equation of straight line is:</b></summary> 

```
    (y-y1) / (y2-y1) = (x-x1) / (x2-x1) 
=>  (y-f(a)) / (f(b)-f(a)) = (x-a) / (b-a)
For(x0, 0) *//if this the root//*
    =>  (0-f(a)) / (f(b)-f(a)) = (x0-a) / (b-a)
    =>  (x0-a) (f(b)-f(a)) = -f(a) (b-a)
    =>  (x0-a) (f(b)-f(a)) = af(a)-bf(a)
    =>  x0 = a+ (af(a)-bf(a)) / (f(b)-f(a))
    =>  x0 = (af(b)-af(a)+af(a)-bf(a)) / (f(b)-f(a))
    =>  x0 = (af(b)-bf(a)) / (f(b)-f(a))
```

</details>

So, first approximate, x0 = (af(b)-bf(a)) / (f(b)-f(a))

If for x0, f(x0) equals to 0, we get desired root.

Else follow bisetion approach.

1. f(x0) * f(b) < 0
2. f(x0) * f(a) < 0

Need to select the correct one.

<details>
<summary><b>Find a real root of the equation: x^3 - 2x^2 - 4 = 0; a=2, b=3</b></summary>

```
f(a) = -4
f(b) = 5

1st approximate, x0 = (af(b)-bf(a)) / (f(b)-f(a)) = 2.4444
f(x0) = -1.34430727

Since, f(x0) * f(b) < 0
2nd approximate, x1 = (x0f(b) - bf(x0)) / (f(b) - f(x0)) = 2.562162102
f(x1) = -0.309588138

3rd approximation, x2 = (x1f(b) - bf(x1)) / (f(b) - f(x1)) = 2.587691337
f(x2) = -0.064732741
......
..... Need to write all the steps in exam! Calculating via calculator

12th approximationm x11 = (x10*f(b) - b*f(x10)) / (f(b) - f(x10)) = 2.594313012
```

</details>

**🎈Newton Raphson Method**

Starts with approximate value in order to find a value as close as root.

x1 = x0 + h *h is very small, tends to zero, can be pos or neg*

f(x1) = f(x0+h)

<details>
<summary><b>Expansion by Taylor's series:</b></summary> 

```
    f(x0) + h f`(x0) + h^2/2! f``(x0) + .... = 0
=>  f(x0) + hf`(x0) = 0 *Neglecting vlaues of higher derivatives, as they are very small*
=>  h = - (f(x0) / f`(x0)); f(x0) != 0 *if 0, then already got the soln*
```

</details>

So, 1st approximation, x1 = x0 - f(x0) / f`(x0)

Xn+1 = Xn - f(Xn) / f`(Xn); n = 0,1,2,3.....

*H.W. Geomteric Expansion; Derivative, slope related*

<details>
<summary><b>x^3-2x^2-4; a=2, b=3</b></summary>

```
X0 = 2.5 //using previous root finding methods.. Bisection: (a+b)/2 or from false position method

X1 = X0 - f(X0)/f`(X0) = 2.6

x2 = x1 - f(x1)/f`(x1) = 2.594331984
....
...

x5 = 2.594313016
```

</details>

*In Bisection method, approximate root swing both ways. But in False Position & Newton-Raphson method, in first approximation, we know in which side root is. less iteration.*

</details>

<details>
<summary><h2>Lecture-05: 19th September</h2></summary>

</details>

<h2>Lecture-06: 17th October</h2>

<h2>Lecture-07: 24th October</h2>