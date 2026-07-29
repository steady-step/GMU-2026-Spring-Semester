# Week2 keypoint

## basic theory

    .m -> matlab file extension.
    
    markdown file name -> only alphabet + number + _ . Also, we should start the file name only with alphabet.

    other symbols are not admitted. (! etc) Capital letter and small letter are separated.

    .docx -> word file extension.

    .pdf -> pdf file extension.

    folder = directory

    syntax : a grammer for making sentence combining word. (it is also used in programming language!)

    Base 10 -> each digit is range from 0 ~9. so Base 2 -> each digit is 0 or 1.

    1 bit -> 0 or 1, 1 byte = 8 bits, 1 word = 32 bits

    Computer only use bits considering the sturcture of logic gate.

    N bits can make 2^n patterns. (ex: 8bits -> 256 signals)

    it is also used for making a color bits.

    Ascii code -> A code for indicating letter. it is made up of 7 bits. and it can indicate 128 letters.

    Extended ascii code -> 8 bits ->256 letters.

    Unicode -> Main way for indicating letters now. 16 bits. 

    1 kb = 2^10 byte. 1MB = 2^20 BYTE. 1GB= 2^30 BYTE.

    

## Basic of Matlab

    disp function is for printing.

    we can print letter without disp. But in this situation, variable name is also printed.

    (if it doesn't have name, ans= is printed)

    we can make variable like this -> a=5, d=3, b=d b=b+1

    ; means that it prohibit printing the return value if it is used at the last of the line. but In the disp, letter is printed becuase disp is not related to

    return value. Also, the sequense of the calucating is like this -> () <inside ->outside> -> ^ -> * / -> + -( if the sequense is same, calculate left to right)

    Also, there are many fuctions. ex) pi(print pie), sin(x), cos(x), sqrt(x)(root x), exp(x) (e^x), logx(ln x), log10(x), mod(x,y) (remainder), abs(x) (|x|).
    

## Data structure and type of Matlab

    In the Matlab, there are 6 data types. Numeric, Logical, char, string, Datetime, Categorical.

    Numeric means number. it also exists pi, infinity, integer, decimal number, NAN(it is combined word with non-exist and mathematically being impossible. (3/0)

    Logical means logic values such as True, False.

    char is just one character and we write this character with ' '. Also, when calculating, we use unicode. 

    string is one or more characters we write string with " " .

    Datetime is a special type and we can make this type with datetime fuction.

    Categorical is special type simillar with factor in R. 

    Also, variables in matlab can store 5 types. array, cell array, struct, table, fuction(with @). They are data structure.

    First one is array. Array is composed of same type, and the unit is 1x1 array. 

    For example, numeric array : A = [1,2;3,4], Logical array: L=[true, false;true,false], char array : c='hello', c=['tom']

    string array : s=["TOM","JO"], datetime array : D= [datetime(2026,1,1);datatime(2026,1,2)]

    When analyzing these, for making one or two dimensional array, we use [], and , means to expand the rows, and ;means to change the columns.

    There are no scalas in Matlab. 'hello' is also 1x5 char arrays. and the length of this s= "TOM" vector is 1 (because it is string, not char.)

    There are no limits in array dimensions. For making 3+ demensions, I will introduce two ways.

    1. A(:,:,1) = [1,2;3,4], A(:,:,2)=[3,4;5,6]

    2. use cat fuction. cat(3,m1,m2,m3) , 3 is demension, m1,m2 m3 is a 2 demension arrays. 

    Like this, We can expend the demension. 4 demension? it is not difficult. it is just to make a 1xN table and each context has 3 dimension arrays.

    Categorical : it is similar with factor in R. we can define it like this -> A= categorical(["a","b","c","d"]) in (), we can insert string array,

    char array or cell array(all components should be just 1x1 arrays) and there are two layers in that. first one is just label. (A,B,C)

    and second one is index connected with label. and printing that, we can see the characters except " ". it means it is not char or string. 

    They are categorials and they just connect index to labels for printing. it is categorical.

    ex) A= categorical(["A","B","C","D"]) -> A -> A B C D (except "") and the inside, the index is 1 2 3 4 and the label is A B C D.

    Next, cell array is similar with array but difference is to store all kinds of things including struct, table, cell array, array, categorial fuction etc.

    We define it like that c= {"a",1,[1,2,3]} and the way for extending dimension is same with arrays.

    struct is one dimension structure. we can made each name in the space and we can store sturct, table, array, fuction etc.

    We can define like this S.name = "G", S.age=25 or we can use struct fuction. S=struct('g',100)

    it is similar concept with pointer in C.

    Last, it is table. we can assign the context of columns like this. T= table(a1,a2,a3) each variable can be array or categorial, cell, struct or table.

    they are placed at each columns and if the dimension is over 1, rest of the context is stored in the one spot sorted by rows.
     

# Other concept

    In the Matlab, the special fuction exists.

    Usually for calculating, it should be same with data structrue and data size.

    but it is exception. between array caculation,(not when creating.)

    if the demension is 1, we can extend the range through copying.

    ex) 1x2 + 3x2 = 3x2(extending) + 3x2 = 3x2

    we just copy 1x2 three times under the row.

    Also, array can calucalte if the size is same, but categorical, struct, cell array, table is usually impossible to calucalte.

    But, categorical and table can calculate only when ==.

    1. categorical -> we consider it as arrays. so, we compare it with char, string, and categorical arrays. the laws above them can be used.

    (such as 1x2 + 3x2 = can be extended) the result is logical array.

    2. table -> we can compare it with table and 1x1 array. we can not extend the range.

       the result is logical 2-demension array.




    

















    





    


























    
  
