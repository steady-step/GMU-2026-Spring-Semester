# Week5 keypoint

Week5 is mid-term week. Although there are no additional chapters in this week, I study confusing points of Matlab.

## Confusing points

    Matlab' merit is it can do matrix calculation.

    The structure which has demension over 2 is just considered as array not matrix.
    
    So, they can not use A*B, A/B, A^B, etc. (only use A+B,A-B,A.*B...) and A+B is just element calculation.

    But, the calculation which is occured in structure which has demension 1 or 2 is considered as matrix one.

    Therefore, A+B is matrix calculation although it looks same with element calculation. and 2 demension one can use a*b a/b etc...

    The singal A.+B is impossible. But, A.*3,A*3 both are possible.

    It means a*3 is considered as a.*3 even if you don't use dot.

    Also, in array calculation, extension and element caluclation are occured naturally.

    But, in matrix calculation, extension is only occured in addition, subtraction, element calculation and constant multiplication and division.

    in R, ':' makes row vector and if we make empty box when indexing, it means selecting all.

    in Matlab ':' makes also row vector and if we type : it means selecting all.

    In matlab, there are 3 types for indexing... (), {}, dot.

    () means just extracting them maintaining outer form. We can extract multiple index, and if you want to use colnames,

    you can use  '', or "", and if it is numerous, you can also use cell array, char array and string array.

    {} means just extracting them destorying outer form. you can extract numerious things, but it just prints each element

    disassembling with 1x1 matrix. ex) a{1:3} -> 1, 2, 3 (each element) if you combine them, use [] or {} out of them.

    But, in table, if the extracting thing is just col vector, it automatically changes to their form.(not devide into 1x1 matirx)

    . can use in struct for extracting the data. ex: a.data

    it also can be used in table only based on colnames. ex: a.col1

    . can only extract one column and element in struct. Also, the outer structure is destroyed.

    When making plot in matlab, we usually use title, xlabel, ylabel function.

    In that function, We can use '(char) and "(string) both. ex) title('a'), title("a")

    

    









    
    

    
