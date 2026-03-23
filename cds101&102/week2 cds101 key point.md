# week2 cds101 key point


## data type and structure of R

    There are 6 data types in R. numeric, integer, logical, complex, character, raw.

    numeric is just a real number and there is NAN which means there does not exists in the mathematics(such as 0/0), 
    
    integer is written as 3L for dividing into numeric. logical is composed of true, false, and na (na means the empty value)

    complex is imaginary number and raw data is just a pure 1 byte binary data for being used as command, file etc.

    Also, variable can store data types + fuctions. (vector, list, matrix, dataframe, factor, array, fuction)
    
    So, I will introduce 6 types for storing data. in R, scalar does not exists. 1 is a vector which has the length of 1.

    Vector is 1 demension structrue and it is composed of same 1 length of vector with each space. we define like this -> c(1,2,3), c("a","b","c").

    matrix is 2 demension structure and it is composed of same 1 length of vector with each space.

    array is 3 over demension structure and also it is composed of same 1 length of vector with each space.
    
    these 3 can calucalte if the type is same. but the next 3 can't calculate usually.

    list is one demension structure and it can store all things including fuction list, vector, matrix, dataframe etc.

    data frame is two demension structure and it can store vector, list, matrix, factor. For making that, we make all vector, list etc for each columns.

    and we insert them for each columns. vector and factor is no problemm because it is one demension but dataframe and matrix have problems.

    For resolving this problem,  multi column data is nested into a single column spot, allowing a table-within-a-table structure.

    Last, factor. it is special vector. we define like this a<- factor(c("a","b,"a")) Like this, we can insert integer, numeric,logical, character vector in that.

    After inserting that, there are two layers. first layer is index(number) made by factor. and second layer is the labels. 

    This is example.    1 2 1  , a b  in this, a b means the label and each means 1,2 and 1,2,1 is the index. and when we print that, we can see like that

    a b a
    levels : a b       the index is changed to letter but there is no  " ". it means they are not character. and levels means the labels.

    the representative type is a b a. so if you want to change the type, a b a is changed. if you changed it to numberic -> 1 2 1.

    to character "a" "b" factor a b is different with character "a" "b".

    Last, vector, matrix, arrays, and factor are composed of just 1-size vector.(also when defining).

    they have specific number(1+2i), logical(true), character("ABC"), factor(non "")

    Although we write vector c inside c for many times like that c(c(c(1,2,3)), the r studio invert that to c(1,2,3).


## other special information

    When caculcating each other, you should use same type and same size (vector, size 3)

    but there are some exception.

    1. if vectors are caculated each other, small size can be changed to large size to this ways.

      1 2 7   +  1 2 5 3 6  -> 3 vs 5 therefore, we copy 1 2 7 to be a same length with 1 2 5 3 6

      so, 1 2 7 1 2 + 1 2 5 3 6

    2. array matrix can use length=1 vector when creating and cacluating.

    3. when we make dataframe, if the length of vector or factor is less than rows and the length x k = row ( k is positive integer)

       we can copy vector or factor for increasing them.


    Also, factor and dataframe only can do == this calucation.

    1-1. factor(we can consider it like character vector) vs character vector -> use vector extending laws(1) and make logical vector.

    1-2. factor vs factor -> use vector extending laws and make logical vector.
    
    2-1. dataframe vs dataframe -> make logical matrix

    2-2. dataframe vs length=1 vector -> make logical matrix.


## basic of R

    Wrtting comment in R -> #

    help(fuction name) -> help fuction, to know how to use this fuction.

    sum(1,2,3,4,5,6,7) -> sum fuction, we can input some vectors.

    mean(c(1,2,3))=2 -> the first vector is key point for making avg. others are just option. If mean(1,2,3) -> we only consider mean(1) = 1

    sqrt(3) = root 3, exp(1)=e^1= 2.7~

    (1+2)*3-4 = 5 this is also one-size vector.

    sam <-  c(1,3,4,5) using variable symbol is <-.

    View() -> visualize data with excel type.

    " " , ' ' is same in R.

    %>% is called as pipe. it belongs to tidyverse package. it helps us to make code on the other way.

    mean(samp) = samp %>% mean

    sd(samp) = Variance

    print(variable) is usually same with variable but, we need print fuction especially in in loop statement.

    x<-13:17 (make continious vector, interval =1) c(13,14,15,16,17) (integer)

    if the either end is not integer, the vector is numeric. ex)x<-13.5:16.1

    x<-6:1 (decreasing)

    rm() -> remove fuctions on environment

    NA -> No value in the space

    NAN -> it is impossible in mathematics. (0/0)

    Null -> the space doesn't exist.

    class() -> watch type.

    Type change

    1. type changing with as fuction -> as.type(x) such as as.integer(x)

       we can get that type version of x, but x type is not originally changed.


    2. vector type changing

       priority : character > complex > numeric > integer > logical > raw

       x<- c(1.7,"a")  1.7 is changed to "1.7" due to that priority.

    3. type changing due to usual calucating(+,-,*,/)

       priority also exists.

       x=True,  x + 10 = 1+ 10 = 11
       
       But, x is not originally changed.

    4. Bit caculating


       previous priority is disappeared.

       1) both are raw -> bit calculating

       2) either is character -> error

       3) rest -> type changing to logical.


    Usual type change except raw

    the result can be 'na' if "abc" to numeric.. it is na(empty). 
     
    Like this, except raw, there are 2 kind of result. exists, na

    1) as fuction -> exists or na

    2) vector -> exists or na

    3) usual calculation -> exists or na

    4) bit calculation -> Logic result or error


    When raw data exists...

    the result can be 'na' or error or existing. Also, raw data can't do usual calculation.(+,-,x,/)

    Only it can do bit calculation.

    1. as fuction -> na or error or exists

    2. vector -> na or error or exists

    3. usual calculation -> X

    4. bit calculation -> Bit result or Logic result or Error


    is.numeric(x) -> make logical vector if each element is numeric -> True, else : False

    is.na(x) -> include nan to True.

    table(x) -> make table about the number of each element.

    if we want to make table like this,
    
    a1 <- c("a","b","b","a")
    
    a2 <- factor(c("a","b","b","a"))

    table(a1) and table(a2) are same.

    a    b

    2    2
    
    the difference for making table(x) with character vector and factor
    
    1. To make table, charcter vector should check all previous-made elements of table for checking whether the elements already have been existed.

       If we assume the number of original element as N, the number of calculation is O(N^2).
       
       because we check approximetly n times for previous-made elements of table per the number of original element. so, N*N=N^2.

       But for making factor, first we check the labels and adds the number 1 at the element of table. we can represent the number of calculation as O(N),

       Because we immediately increase the number of element of table after checking labels. 
       
       So, we just calculate approximely N(the origin element number) for succesing. 

       Therefore, factor is much efficient than usual vector.


    2. When using factor, we can add unused elements like this.

    a    b    c

    2    3    0

    this is why r first check the labels. So, if we add special labels into factor, we can make table like this different with usual vector.

    
    
 
       









       

       

       

       




















    
    












    





    






    
