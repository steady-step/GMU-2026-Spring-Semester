# Week4 key point

## Further exploration

    In matlab, We use () for indexing, and we can separate demension through comma.

    Also, you can use multiple indexes through :. 1:3 means [1,2,3].

    ex) (1:3,3,4)

    Like R, there are similar grammer with [[]], $ in matlab.

    they are {} and .(dot).

    {} can extract pure data from cell array etc, and dot can extract pure data from struct, table etc following column lable etc.

    Also, array, categorical and cell array don't use dots.

    But, table and struct use dot.


## Grammer

    for loop is a syntax for iterating some loops.

    the structure is like this.

    for variable = data (ex: n=1:3)

       context

    end

    
    First, the variable exists even after the loop is ended. And the assignment expression is not same with usual one.

    The first data is assigned to variable at the start of the for syntax, and if it is approached to end syntax,

    they check whether the next element exists for assinging to variable. If the element exists, they assign next element to variable.

    And if it doesn't exist, for syntax is ended. For example, if for n=[3,4,5], n is changed three times in for loops.

    and also for is looped for three times. We can utlize this variable not only in for loop but also out of for loop.

    : is useful opeartor for making 1xn array. 1:3 means [1,2,3] and it is also same with [1:3].

    In the data, any dataset can be inserted. but if the demension is 2, variable value is chnaged with column.
    
    for example, if the data set is 1 2
                                    3 4 ,  for loop just repeats two times because the columns ae two, and 

     the variable will be [1,3] and [2.4].

    if the dimension is over 3, it is also based on just columns. So, if we calculate the number of loop,

    mxn -> n(2 demension) mxnxp -> nxp(3 demension)

    ex) for n=1:5
        n
        end      -> n=1, n=2, n=3, n=4, n=5

      for n=1:5  
      n^2
      end       -> n^2 is not variable, so matlab prints ans instead of n

                 ans=1, ans=4, ans=9, ans=16, ans=25

      10:-3:1 = 10,7,4,1

      1:0.4:2 = 1,1.4,1.8

      for n=1:1:3  
      n
      Y(n)=n+1
      end

      In this case, Y is automatically created. It is a special function of R and Matlab.

      First, Y[1] is newly created, and Y[2], Y[3] can also be created increasing n.

      Also, if we just type A[3], it is different with original one(copy one) but A[3]=9 can change the origianl one.

      Y(n)=n+1 can chage the origianl one, and considering the matlab function, it will print all y value at Y(b)=n+1 syntax

      So, the result is : n=1, Y=2, n=2, Y=2,3 , n=3, Y=2,3,4

      IF syntax is conditional statement made by their logical expression.

      the syntax is like this.

      if(logical expression)

      context

      end

      logical expression should have the logical result(TRUE/FALSE) if the result is TRUE, the syntax is executed.

      There are many operators in Matlab. == ~=, <, > >= <=, &&, || ~ etc.

      The operator precedence is like this. () -> Arithmetic(^ -> * / -> +,-) -> Relational -> Logical(~ -> && -> ||)...

      If the procedence is same, calculate from left to right.

      If else -> if the 'if' condition is not satisfied, else syntax is executed.

      They exist in same location.

      if()
      
      else()
      
      end

      if elseif elseif...... it is also set. If even one condition is satisfied, the other conditions are not considered.

      They also exist in same location.

      if()
      
      elseif()
      
      elseif()
      
      end

      if elseif elseif else : it is also set... else is a final destination.

      They also exist in same location.

      if()

      elseif()

      elseif()

      else()

      end

      nest if is possible like this

      if()

        if()

          end

      end


      but is is impossible to insert two if in one end.

      if()

      if()    -> impossible.

      end     


      ex)

      c=1;

      for a=1:3  
        if(a<=a^2)
             c=c+1
    end

    c   

    result : c->4



      

      

      

      








      
    











  

    
