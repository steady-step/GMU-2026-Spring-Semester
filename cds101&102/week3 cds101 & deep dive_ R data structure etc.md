# Week 3 key points

## Structure of R data structure

    R data structure is composed of header and data. In header, there are length etc, and a pointer for attributes.

    If you go to the pointer address, there are TAG, CAR, AND CDR. TAG means what recent attribute is (dim etc.), 

    CDR contains pointer for finding next attributes. (You can imagine linked list.)

    CAR also contains pointer for finding main source about this attribute. For example, I will present names attribute in vector.

    If you go to the pointer address of CAR, there are basic header(length and type) and body. In body, there are also pointers. 

    And the number of the pointer is same with the length of the vector. You can also go to the address through pointer.

    Major attributes : names, dim/dimnames, levels etc.

## Grammar

    For creating matrix, we use this function. matrix() in that, we can insert data, nrow, ncol, byrow, dimnames.

    Data should be just one value and nrow, ncol means the number of col, byraw means whether you make the matrix with row order or column order.

    Dimnames should be a list which has two element(row label, and column label -> charcter vector).

    Dimnames is optional, but if you want to make the names, you should fill all names same with the length of row or column.

    ex) matrix(1:6,nrow=2,ncol=3, byrow=TRUE) -> 1 2 3 
                                                 4 5 6

    attributes() -> Print all attributes of data through list.

    dim() -> Print only dim attributes of data.

    cbind -> make matrix tying all presented matrix or vector through column direction.

    rbind -> make matrix tying all presented matrix or vector through row direction.

    For making dataframe, we use data.frame fuction. data.frame(colnames=data,... , row.names = c(), etc...)

    We can insert many types or data and we can make the name as labels.

    ex) data.frame(a=1:5,b=c("A","B","C"),fff = 1:6)

    nrow -> Print the number of the row.

    ncol -> Print the number of column.

    rownames -> print the names of label of row.

    colnames -> print the names of label of column.

    For making list, you just use list() fuction.

    This function is so simple for using. list(names=data,...)

    ex) x<-list(1,"a",TRUE,1+4i)

    class() -> Print the class attributes

    index -> [] or [[]] or $

    [] -> maintain its original data structure

    a[1,2] a[2,] a[,2], a[,], a[2]

    a["b","c"], a["b",], a[,"b"], a["b"]

    a[c(1,2),c(3,4)], a[c("e","b"],c("c","d")],

    if variable d = 3, a[d]

    They are all possible.

    [[]] -> doesn't maintain its original data

    in this form, only one number or colname can be entered.

    ex) a[[3]], a[["col1"]]

    $ -> doesn't maintain its original data

    only colname is possible -> a$colname

    In this form, we don't use " ".

    additional grammar
 
    x <- c("a","b","c","d","e","f")

    x[1] -> "a"

    x[-1] : except x[1] -> "b","c","d","e","f"

    length(x) -> length..

    x[length(x)] "f"

    x[x== "c"] -> first, x=="c" (char vector) is extended to x length. So c("c","c","c","c","c","c")

    And After logcial calculation, it will be (F,F,T,F,F,F)

    And the x[x=="c] -> "c" (just print true index)

    y<-c(1,2,3,4,5)

    y[y>2 & y<4] -> 3



    

    
    

    

    

    


    










    

    

    
        

        

    

    

    

    

    

    

    
