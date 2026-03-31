# Week 3 key points

## Structure of R data structure

    R data struture is composed of header and data. In header, there are length etc, and a pointer for attributes.

    If you go to the pointer address, there are TAG, CAR, AND CBR. TAG means what recent attribute is (dim etc),

    CAR also contains pointer for finding main source about this attribute. For example, I will present names attribute in vector.

    If you go to the pointer address of CAR, there are basic header(length and type) and body. In body, there are also pointers. 

    And the number of the pointer is same with the length of the vector. You can also go to the address through pointer.

    Finally you can find the header(type, length) and the names. We can't know this process when using just R. but R interpreter should use

    so many processes related to pointer. Also, the header in attribute is not same with vector header. You should distinguish these two header.

    It is different. Vector,matrix,array just have a body which contains real information. Factor is also same, but levels is located in attributes.

    Dataframe and lists are different. It is important. In their body, they just have a pointer about that. and We also should find the real informatin through pointer.

    I will introduce major attributes : names(vector), dim/dimnames(matrix), levels(factor).

    Name means the labels of each element, and dim means dimension of that. dimnames is labels of that.

    Dataframe doesn't have dim, but we can know that indirectly. They just have pointers in body. and the number of pointer is same with the number of columns.

    Also, the number of columns can know the header's length section (it is not attribute. it is important.)

    And we can know the all datas through finding deeper investigation. There are some pointers for each column if you go deeper. 

    Through these processes, we also can know the number of row.

## Grammer

    For creating matrix, we use this fuction. matrix() in that, we can insert data, nrow, ncol, byraw, dimnames.

    Data should be just one vector and nrow, ncol means the number of col, byraw means whether you make the matrix with row order or column order.

    Dimnames should be a list which has two element(row label, and column label -> charcter vector).

    Dimnames is optional, but if you want to make the names, you should fill all names same with the length of row or column.

    In other words, you can make it empty but if you want to make name, you should fill all things. but you don't need to fill row and column simultaneously.

    ex) matrix(1:6,nrow=2,ncol=3, byrow=TRUE) -> 1 2 3 
                                                 4 5 6

    In fuction, if the order is clear, we don't need to use nrow=, ncol= dimnames= etc.

    Also, if we don't insert data, it is filled with NA.

    attributes() -> Print all attributes of data through list.

    dim() -> Print only dim attributes of data.

    cbind -> make matrix tying all presented matrix or vector through column direction.

    rbind -> make matrix tying all presented matrix or vector through row direction.

    For making dataframe, we use data.frame fuction. data.frame(DATA,raw.names, etc...)

    We can insert many datas different with matrix, and we can make the name as labels.

    dataframe is made with column direction, so if you add row.names -> row labels is added(character vector)

    ex) data.frame(a=1:5,b=c("A","B","C"),fff = 1:6)

    In dataframe, factor, dataframe and list also can be inserted. Also similar with matrix, you can make the names, 

    But if you decided to make them, you should fill all things.

    If it is empty, matrix is just considered it as NULL, but dataframe just fill it. row label -> integer, column label -> fill it with their laws.

    nrow -> Print the number of the row.

    ncol -> Print the number of column.

    In R, you should use " " except variable.

    but,3 cases are allowed not to use " ".(you can also use " " )

    In labels of data,

    #1 use $ symbol

    #2 a fuction which is already assigned the dataset (qplot(x=a,y=b,data=c) b is just a column of c.

    #3 When defining df. -> df(a=1:3)

    The labels of the data structure are considered characters. Although the row labels of data frame is integer,

    It is just forms in header, we just use it like character (" " , if you use rownames -> it is printed as character.)

    rownames -> print the names of label of row.

    colnames -> print the names of label of column.

    For making list, you just use list() fuction.

    This fuction is so simple for using. list(names=data,...)

    ex) x<-list(1,"a",TRUE,1+4i) the names are optional. Also, you can just add the names freely. Adding all names for element is not essential.

    class() -> Print the class attributes

    index -> use []. if you use A[1], this is just to make new data sturcture(length=1) it is important. It doesn't view the data. They make their own structure.

    And, [] means to divide the demension, and you can just 

    


    










    

    

    
        

        

    

    

    

    

    

    

    
