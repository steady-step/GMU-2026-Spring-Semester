# Week 10 key point

## Things to know before

There are many Indeterminate Forms in limit condition.

Representatively, 0/0 and ∞/∞ forms exist.

Also, ∞/-∞, -∞/∞ -∞/-∞ are all classified as ∞/∞ form.

## L' hospital's Rule

If f and g have at least one interval at which there are all differentiable and g'(x) ≠ 0,

(when lim x->a, the interval is open interval including a, lim x->a+, (a,b), lim x->a- : (c,a), lim x-> ∞ : (m,∞)

(b,c,m are real number variable)  (a can be possibly excepted)

lim x->a+,a-,∞,-∞,a f(x) =0, lim g(x) = 0 or lim f(x) = +-∞, lim g(x) = +-, -+∞,

right side's limit value exists or +-∞,

lim f(x)/g(x) = lim f'(x)/g'(x)

ex) lim x->1 lnx/(x-1) -> (1/x)/1 = 1

**We can not assume the right side limit value exists when using L' hospital's Rule many times,**

**but, if the value finally exists, we can utilize the result.**

**If it is not, it doesn't mean it doesn't have limit value. We should use other way for checking whether the limit has value.**

## 0x∞, ∞-∞ form

There also exists other four Indeterminate Forms.

We will first deal with how to resolve 0x∞ and ∞-∞

**∞ x 0 : For resolving this form, we just change this to ∞/∞ or 0/0.**

ex: lim x->0+ xlnx = lim x->0+ (lnx)/(1/x) = 0 (∞/∞ form)

**∞-∞ : For resolving this form, we change this also to ∞/∞ or 0/0 through converting to a common denominator** 

lim x->1+ (1/lnx - 1/(x-1)) = lim (x-1-lnx)/(lnx(x-1)) (0/0 form)

## 0^0,  ∞^0, 1^∞ form

For resolving this, there are two ways.

1. using natural logarithm

2. using e^ln(~) (By properties of logarithms)

Also, Lastly utilize Theorem on limits of composite functions.

### Theorem on limits of composite functions

If function g has limit value (L) and f is continuous at L,

lim(f(g(x)) = f(limg(x)) = f(L)

Below is solution process of lim x->0+ (1+sin4x)^cotx

Two ways are all uploaded.























