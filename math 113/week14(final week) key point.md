# Week 14 key point

## Substitution Rule for indefinite integral

**If g is differentiable at x range, and f is continuous at g range,**

By FTC1 & Chain rule,

$\int f(g(x))g'(x) \ dx = F(g(x)) + C$

In this situation, if we set u = g(x),

$\int f(g(x))g'(x) \ dx = \int f(u) \ du$

This is substitution rule for indefinite integral.

But, when analyzing above equation, g'(x) dx becomes du!!

Although in integral sign, dx is not original meaning, 

but we can change g'(x)dx to du when calculating as the result is same.

So, it is key point for calculating integral easily.

After substituting any part of equation to another variable,

if you change other part so that it satisfies substitution form,

we can easily calculate integral.

ex1)

<img src="week14_file1.jpg" width="800"> 

As conditions of substitution rule for indefinite integral are satisfied,

(x^4+2 is differentiable for all real number x, cos function is continuous for all real number)

we can use substitution rule.


ex2)

<img src="week14_file2.jpg" width="800"> 

As conditions of substitution rule for indefinite integral are satisfied,

(5x is differentiable for all real number x, e^ function is continuous for all real number)

we can use substitution rule.


## Substitution Rule of definite integral

**If g' is continuous at [a,b], and f is continuous at g range,**

By FTC1 & Chain rule,

$\int_{a}^{b} f(g(x))g'(x) dx = [F(g(x))]_{a}^{b}$

In this situation, if we set u = g(x),

$\int_{a}^{b} f(g(x))g'(x) dx = \int_{g(a)}^{g(b)} f(u) du$

This is substitution rule for definite integral.

Also, we can utilize this rule as we did before in indefinite section.

ex1)

<img src="week14_file3.jpg" width="700"> 

As conditions of substitution rule for definite integral are satisfied,

((3-5x)' is continuous at [1,2], 1/(t^2) is continuous at [-7,-2])

we can use substitution rule.

ex2)

<img src="week14_file4.jpg" width="700"> 

As conditions of substitution rule for definite integral are satisfied,

((lnx)' = 1/x is continuous at [1,e], t is continuous at [0,1])

we can use substitution rule.












