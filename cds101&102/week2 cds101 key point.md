# week2 cds101 key point


## data type and structure of R

    There are 6 data types in R. numeric, integer, logical, complex, character, raw.

    numeric is just a real number and there is NAN which means there does not exists in the mathematics(such as 0/0), 
    
    integer is written as 3L for dividing into numeric. logical is composed of true, false, and na (na means the empty value)

    complex is imaginary number and raw data is just a pure 1 byte binary data for being used as command, file etc.

    Also, variable can store data types + fuctions. (vector, list, matrix, dataframe, factor, array, fuction)
    
    So, I will introduce 6 types for storing data. in R, scalar does not exists. 1 is a vector which has the length of 1.

    Vector is 1 demension structrue and it is composed of same 1 length of vector with each space. we define like this -> c(1,2,3), c("a","b","c")

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


## other special information

    When caculcating each other, you should use same type and same size (vector, size 3)

    but there are some exception.

    1. if vectors are caculated each other, small size can be changed to large size to this ways.

      1 2 7   +  1 2 5 3 6  -> 3 vs 5 therefore, we copy 1 2 7 to be a same length with 1 2 5 3 6

      so, 1 2 7 1 2 + 1 2 5 3 6

    2. array matrix can use length-1 vector when creating and cacluating.

    3. when we make dataframe, if the length of vector or factor is less than rows and the length x k = row ( k is positive integer)

       we can copy vector or factor for increasing them.


    Also, factor and dataframe only can do == this calucation.

    1-1. factor(we can consider it like character vector) vs character vector -> use vector extending laws(1) and make logical vector.

    1-2. factor vs factor -> use vector extending laws and make logical vector.
    
    2-1. dataframe vs dataframe -> make logical matrix

    2-2. dataframe vs length-1 vector -> make logical matrix.



    












    





    






    
