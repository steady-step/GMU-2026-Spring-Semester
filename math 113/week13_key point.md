# Week 13 key point

## First Fundamental Theorem of Calculus (FTC1)

When f is continuous at [a,b] and the range of variable x : [a,b],

g(x) = $\int_{a}^{x} f(t) \, dt$ -> g'(x) = f(x)

ex) g(x) = $\int_{0}^{x} \sqrt{1+t^2} \, dt$ , g'(x) ?

if x : [0,∞) -> $\sqrt{1+t^2}\$ is continuous.

Therefore, g'(x) = $\sqrt{1+x^2}\$ ( x : [0,∞))

**Although we can find the derivative at (-∞,0] in another way, we just found only [0,∞) part as this section deals with FTC1.**

ex) g(x) = $\int_{0}^{x^3} \cos(t) \, dt$ , g'(x) ?

x^3 = u =  h(x), h(x) is differentiable in all real number,

g(x) is differentiable when x>=0

therefore, we can use chain rule when x>=0

g'(x) = du/dx * ($\int_{0}^{x^3} \cos(t) \, dt$)' = 3x^2 * ($\int_{0}^{x^3} \cos(t) \, dt$)'

By FTC 1, **g'(x) = 3x^2 * cos(u) = 3x^2 * cos(x^3)** ( x : [0,∞))


## Second Fundamental Theorem of Calculus (FTC2)

This theorem is highlight. 

Thanks to FTC2, we can easily calculate definite integral.

It is proved by FTC1.

When f is continuous at [a,b], 

$\int_{a}^{b} f(x) \ dt$ = F(b) - F(a)

ex) y=x^2, 0 to 1 -> as x^2 is continuous from 0 to 1,

$\left[ \frac{1}{3}x^3 \right]_{0}^{1}$ = 1/3

ex) $\int_{3}^{6} \frac{1}{x} \ dx$ ?

$\left[ \ln|x| \right]_{3}^{6}$ = ln6 -ln3 = ln2

## Indefinite Integrals

Signal : $\int f(x) \ dx$

Meaning : The set which has all functions whose derivative is f(x).

So, it is a set. Not function.

So, we can represent this set through set-builder notation,

ex)

$\left\{ y = \frac{1}{3}x^3 + c \mid c \text{ is any real number, } x \text{ is the independent variable, } y \text{ is the dependent variable} \right\}$

So, we write this set-builder notation simply like these :

$\int f(x) \, dx$ = F(x)+ C 

$\int f(x) \, dx$ = 1/3 x^3 + C

So, this set is called as indefinite integrals.

ex)

$\int x^2 \, dx = \frac{1}{3}x^3 + C$

$\int \frac{1}{x} \, dx = \ln|x| + C$

$\int x^n \, dx = \frac{x^{n+1}}{n+1} + C \quad (n \neq -1)$

**C is called as constant of integration.**

Also, the simplified expression can be calculated each other by this rule :

$\int cf(x) \, dx = c \int f(x) \, dx$

$\int [f(x) \pm g(x)] \, dx = \int f(x) \, dx \pm \int g(x) \, dx$

ex) $\int (10x^4 - 2\sec^2 x) \, dx$ ?

By above rule,

$\int (10x^4 - 2\sec^2 x) \, dx = 10 \int x^4 \, dx - 2 \int \sec^2 x \, dx$ 

= 2x^5 -2tanx + C

## The Net Change Theorem

$\int_{a}^{b} f(x) \, dx = F(b) - F(a)$ 

∵ f(x) = F'(x),

it can be $\int_{a}^{b} F'(x) \, dx = F(b) - F(a)$

we can know the integral of a rate of change is the net change.

This is Net Change Theorem.

This theorem is typically used in distance, speed and time relationship.

$\int_{t_1}^{t_2} a(t) \, dt = v(t_2) - v(t_1)$

$\int_{t_1}^{t_2} v(t) \, dt = s(t_2) - s(t_1)$ (displacement)

$\int_{t_1}^{t_2} |v(t)| \, dt$ (distance)

ex) A particle moves along a line so that its velocity at time t is

v(t) = t^2-t-6  (m/s)

1<=t<=4, displacement? -> v(t) graph is continuous at [1,4].

Therefore, by Net Change Theorem,

$\int_{1}^{4} (t^2 - t - 6) \, dt = \left[ \frac{1}{3}t^3 - \frac{1}{2}t^2 - 6t \right]_{1}^{4} = -\frac{9}{2}$




































































    



