# week3 keypoint

##  Matlab grammar

    Comment : use %, comment is ignored when executing. the code's color is green.

    scalar : just one value

    vector : connect several values as data structure. (one dimension)

    row vector : A=[1,2,3] or A[1 2 3] or 1:3   

    column vector : A[1;2;3]

    vector index : (), A(8)=12, A(2)=7 etc.

    In matlab, vector is actually array.

    Array is similar with vector in R.

    In other words, Array in Matlab is vector in R which can also extend its dimension even to 3 or 4.

    In array, each dimension's size can be extended if its size is 1.

    A + 3 -> 3 is just 1x1 array, and the size is extended same with A. and matrix is calculated.

    In matrix, *, ^, / calculation is not same with usual one.

    it is followed with matrix calculation. if we type A*B -> the result is not multiplication result with each element.

    So, if we want to multipy each element, we use .(dot) A.*B, A./B, A.^2 etc.

    Exception : A * 3 -> by extension law, it is extended and the calculation is impossible

    as matrix calculation should be performed. But, this one is performed like usual calculation (important)

    Fuctions in matlab -> sqrt(): root, exp() : e^x, log():  loge, log10() : log10, sin(): sinx(radian), mean() (average), std() : standard deviation

    e : 2.7~, but in scientific Notation, e+yy means 10^yy, e-yy means 10^-yy. so if 1.2e+03 -> 1.2 X 10^3= 1200

    plot(x,y) -> making plot with point(x,y) and connect them through line.

    length(x) = the length of x 

    We can make code like this -> plot(1:length(P),P)

    Figure function can make or change own graphic window for drawing graph.

    if we type like this : figure(2) -> figure 2 is newly created or if it is already created, the figure is changed.
    
    title('') is just a fuction for making a title, and xlabel and ylabel are a fuctions for making labels.

  






    













    

    
    

    














    





    

    
