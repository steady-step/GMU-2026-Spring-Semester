# Week3 keypoint

## Power law 

    When lim x->a f(x)=L, n : positive integer ,  lim x->a (f(x))^n = (lim x->a f(x))^n = L ^n 

    We can prove this law with limit laws. because of limit laws, lim x->a (f(x))^n = lim x->a f(x)*lim x->a f(x)....

    Therefore, the result is same with L^n.

## Root law

    When lim x->a f(x)=L, n: positive integer, lim x->a n root f(x)= n root(lim x->a f(x))= n root L

    This law can be proven by power laws. we assume lim x->a n root f(x) as K. 

    To exist K, if n is even, L should be over 0. (proven by n root x graph)

    k^n = (lim x->a n root f(x))^n (by power law)= L so k^n=L, k= n root L. 

    Therefore, lim x->a n root f(x) = n root L = n root lim x->a f(x).



### the law made by power and root law

    if F is polynomials or rational, and a is domain of f, lim x->a f(x) = f(a)

    other fuction : use limit, power, and root law for calculating lim.



## Comparison Theorom 

    If  lim x->a(or x->infinity) f(x) = L, lim x->a (or x->infinity) g(x) = M,

    and f(x)<=g(x) or f(x)<g(x), 
    
    ( range of x (x->a) : k>0, k exists. in the range of (a-k,a) and (a,a+k), all f(x)<=g(x) or f(x)<g(x))

    (range of x (x->infinity) : k is real number, k exists in the range of (k,infinity), all f(x)<=g(x) or f(x)<g(x))

    L <= M
    

## Continuity of function


    If f is continuous at a, there are 3 conditions

      1. f(a) exists.

      2. lim x->a f(x) exists.

      3. f(a)= lim x->a f(x).

    Also, we define right-continuity and left continuity like this.

    f(a)=lim x->a+f(x) ->(right continuity)

    f(a)=lim x->a-f(x) -> (left continuity)

    If f is continuous in the interval :

       open interval -> all numbers in interval are continuous.

       close interval -> open interval condition + only left or right continuity for corner number.

    
    if f and g are continuous at a, c is constant -> f+g, f-g, cf, fg, f/g(g is not 0) is also continuous at a.

    we can prove this law with limit laws.

    when the limit laws, 

    exist + exist -> exist

    exist + non exist -> non exist

    non exist + non exist -> unknown

    Like this, when the continuous laws,

    continuous + continuous = continuous

    discontinuous + continuous = discontinuous

    discontinuous + discontinuous = unknown.

    these fuctions are continuous in the domain.

     -> polynomials, rational, root, trigonomatic, exponential, logarithmic, inverse trigonomatic fuction.

     Continuous of composition of fuctions 

      if g is continuous at a, and f is continuous at g(a),
      lim x->a f(g(x))= f(g(a)) , this composition is continuous at a.


    In the continuous law at composition,

      continuous + continuous = continuous

      continuous + discontinuous = 99% discontinious ( except constant fuction)

      discontinuous + discontinuous = unknown.














    
      









   
    











   

    
