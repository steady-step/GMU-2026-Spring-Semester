# Week2 cds101 key point


## Data type and structure of R

    There are 6 data types in R. numeric, integer, logical, complex, character, raw.

    Numeric is just a real number and there is NAN which means there does not exists in the mathematics(such as 0/0), 
    
    Integer is written as 3L for dividing into numeric. Logical is composed of true, false, and NA (NA means the empty value)

    Complex is imaginary number and raw data is just a pure binary data for being used as command, file etc.

    Also, variable can store data types + functions. (vector, list, matrix, dataframe, factor, array, function)
    
    So, I will introduce 6 types for storing data. in R, scalar does not exists. 1 is a vector which has the length of 1.

    Vector is 1 dimension structure and it is composed of same 1 length of vector with each space. we define like this -> c(1,2,3), c("a","b","c").

    matrix is 2 dimension and array is 3 dimension.
    
    these 3 can calculate if the type is same. but the next 3 can't calculate.

    List is one dimension structure and it can store all things including function, list, vector, matrix, dataframe etc.

    Data frame is two dimension structure and it can store vector, list, matrix, factor per each column.

    Last, factor. it is special vector. we define like this a<- factor(c("a","b,"c")).

    After inserting that, there are two layers. first layer is index(number) made by factor. and second layer is the labels. 

    This is example.    1 2 1  , a b  in this, a b means the label and each means 1,2 and 1,2,1 is the index. and when we print that, we can see like that

    a b a
    levels : a b       the index is changed to letter but there is no  " ". it means they are not character. and levels means the labels.

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

       x<- c(1.7,"a")  1.7 is really changed to "1.7" due to that priority.

    3. type changing due to usual calucating(+,-,*,/)

       priority also exists.

       x=True,  x + 10 = 1+ 10 = 11
       
       But, x is not originally changed.

    is.numeric(x) -> make logical vector if each element is numeric -> True, else : False

    is.na(x) -> same with above when na.

    table(x) -> make table about the number of each element.
    
    
 
       









       

       

       

       




















    
    












    





    






    
