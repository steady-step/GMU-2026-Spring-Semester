# week5 key point

    if f(x)=c, f'(x)=0... You can easily prove this with differentiation process.

    f(x)=x^n, f'(x)=nx^n-1.. (if n is natural number.)

    proof : lim x->a x^n-a^n/x-a = (x-a)(x^n-1+x^n-2*a .....xa^n-2+a^n-1)/x-a = x^n-1.....
           f'(a) = a^n-1*n = n*a^n-1, f'(x) = n*x^n-1..

    this formula is also valid in all real number.

    if f(x) is differentiable, (cf(x))'=c f'(x)..

    proof : lim h->0 cf(x+h)-cf(x)/h = c lim h->0 f(x+h)-f(x)/h (by limit law) = cf'(x)

    if f(x) and g(x) are differentiable, (f(x)+g(x))'=f'(x)+g'(x) (f(x)-g(x))'=f'(x)-g'(x)

    proof : lim h->0 f(x+h)+g(x+h)-f(x)-g(x)/h = lim h->0 f(x+h)-f(x)/h + lim h->0 g(x+h)-g(x) (by limit law)

    therefore it is same with f'(x)+g'(x).. This proof process is same when being subtraction formula.

    if we differentiate exponential fuction, the result is b^x * f'(0)...

    We define e^x as f'(0)=1.... E is also same with the value (lim n->infinity (1+1/n)^n) -> when we receive 100% bank interest divided infinitely in 1 year.

    We can also get this expression in e^x one.. f'(0) = lim h->0 e^h-1/h = 1 , e ~lim h->0 (h+1)^1/h , if we assume 1/h = n, lim n->infinity (1+1/n)^n

    It is same with bank interest case!

    As f'(0)=1, (e^x)' = e^x..

 <img src="week5_file1.png" width="200">

    if f and g are differentiable, (fg)'=fg'+gf'

    we assume u=f(x), v=g(x) 

    Δuv = (u+Δu)(v+Δv)-uv= uΔv + vΔu +ΔvΔu

    lim Δx->0 Δuv/Δx = lim Δx->0 (uΔv/Δx + vΔu/Δx + ΔuΔv/Δx)

    (∵v and u are diffentiable, by limit law)

    (ulimΔx->0 Δv/Δx) +(vlim Δx->0 Δu/Δx) + (Δu) * (lim Δx->0 Δv/Δx)

    = u'v + v'u + 0 x v' = u'v + v'u

    if f and g are diffentiable,

    (f/g)' = gf'-fg'/g^2

    proof :  u=f(x), v=g(x), Δ(u/v) = (u+Δu)/(v+Δv)-u/v = (vΔu-uΔv)/(v(v+Δv))

    (u/v)' = lim Δx->0 (u/v)/Δx = lim Δx->0 ((v * Δu/Δx) - (u * Δv/Δx))/v(v+Δv)

    (∵v and u are diffentiable, by limit law)

    = (v*u' - u*v')/v^2

    f(x) and f'(x) are different function. Although f(x) is composition, f'(x) is not..

    If we want to check the domain of f'(x), there are two steps.

    1. exclude f(x) domain (It can calculate with composition function range, common range(when a+b,a-b,a*b...), presented range(x>5), denominator=0 etc...)

    2. exclude f'(x) domain( it will be cusp or vertical tangent line)


    

    

    
