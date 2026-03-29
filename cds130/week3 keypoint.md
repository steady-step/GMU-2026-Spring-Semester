# week3 keypoint

## r & matlab exception grammar

    R

    1. vector extension law when calculating.

    2. Length 1 vector can be used when calculating and creating in matrix and array.

    3. when creating df, vector and factor can be extended.

    4. automatic form change in vector, matrix and array.

    5. automatic form change when calculating.

    6. vector, list, factor can be extended with NA and NULL if index-overed element is defined.
    
    ex) the length of A is 5. but A[8]=10 -> A[6],A[7] = NA (Automatic extension)

    Matlab

    1. Array extension when calculating.

    2. autnomatic form change(array)

    3. automatic form change when calculating

    4. array,and cell array can define without ,

    5. Automatic extension like #6 in R. (array -> 0, cell array -> empty)

    6. pure 1x1 numeric array x array -> just calculate like scalar.

    In matlab, automatic form change is similar with R, but the priority is logical < char < numeric < datetime < string.
    

## grammar

    Comment : use %, comment is ignored when executing. the code's color is green.

    if the comment location is at the head of the line : the line is all comment.

    if the location is middle of the line : comment starts behind of the %.

    scalar : just one value

    vector : connect several values as data structure. (one dimension)

    row vector : A=[1,2,3] or A[1 2 3] or 1:3   

    column vector : A[1;2;3]

    vector index : (), A(8)=12, A(2)=7 etc.

    In matlab, vector is just one-dimension array.

    A + 3 -> 3 is just 1x1 array, and the size is extended same with A. and matrix is calculated.

    A*3, A/3 -> it is exception. we just calculate like scalar.

    vector vs vector(one demension array) -> length should be same.

    In matlab, array is considered as matrix. 

    In matrix, *, ^, / calculation is not same with usual one.

    it is followed with matrix calculation. if we type A*B -> the result is not multiplication result with each element.

    So, if we want to multipy each element, we use .(dot) A.*B, A./B, A.^2 etc.

    Fuctions in matlab -> sqrt(): root, exp() : e^x, log():  loge, log10() : log10, sin(): sinx(radian), mean() (average), std() : standard deviation

    e : 2.7~, but in scientific Notation, e+yy means 10^yy, e-yy means 10^-yy. so if 1.2e+03 -> 1.2 X 10^3= 1200

    plot(x,y) -> making plot with point(x,y) and connect them through line.

    x,y should be array(one or two demension) and the size should be same.

    if x is one demension, and y is two demension : the length of raw should be same with length of x.

    fuction makes each line with different color based on each y's columns.

    when x is two demension, and y is one demension: it is same.

    if x and y are two demensions : the size (row and column) should be same.

    and function makes their own lines connecting their columns each other.

    length(x) = the length of x 

    So I can make code like this -> plot(1:length(P),P)

    Figure fuction can make or change own graphic window for drawing graph.

    if we type like this : figure(2) -> figure 2 is newly created or if it is already created, the figure is changed.

    And, before we change the figure, the program continues to draw the graph in the specific figure.

    title('') is just a fuction for making a title, and xlabel and ylabel are a fuctions for making labels.

    title, xlabel and ylabel should use ' ' because they require char array.

  






    













    

    
    

    














    





    

    
