# Week 3 key points

## Structure of R data structure

    R data struture is composed of header and data. In header, there are length etc, and a pointer for attributes.

    If you go to the pointer address, there are TAG, CAR, AND CDR. TAG means what recent attribute is (dim etc), 

    CDR contains pointer for finding next attributes. (You can imagine linked list.)

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

    For creating matrix, we use this fuction. matrix() in that, we can insert data, nrow, ncol, byrow, dimnames.

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

    For making dataframe, we use data.frame fuction. data.frame(DATA,row.names, etc...)

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

    And, [] means to divide the demension, and you can just insert only one vector for each dimension. Integer vector is needed, but although you insert numeric 

    vector, they automatically changes it to integer. And through [], you can select many datas over one. ex) A[c(1,2,3),3,4] (three dimension for array)

    [] can be used in all data types. In [], there are 3 types which can be inserted.

    1. integer vector

    2. logical vector(the length should be same with the full length), If it is TRUE, the value is printed

    3. Character : use labels (dimnames etc)

    When we use [], R just make the smaller same stucture with previous sturcture.

    If it was Dataframe, A[1,2] is also dataframe.(but it is 1x1)

    If you want to extract pure things in that, use [[]] A[[1,2]]. If the pure data is list, A[1,2] is just data frame, but A[[1,2]] is a pure list.

    It can just extract one value.

    $ is to extract pure data through name labels(dimanmes etc), and combine them with same structure. If it is impossble, it is error.

    Such as, in dataframe, you can try to extract $ with row lables, but it may be error becuase it is mosly impossible to combine them with one structure.

    So, we just use $ in dataframe with col names because we make dataframe with same structure per columns.

    It can be possible if the data type is same. but is is rare. 

    For example, if you want to add vector + vector in list it is impossbile with []. With [], vector in list is just a list (length=1)

    So we should use [[]] or $. Also, the importnat thing is $ can be only used in dataframe, and list. it can be used in vector etc.

    Also, in R, there is automatic fuction for operating like [[]]. in [], we can set the fuction like this drop=FALSE,

    it means that I don't want to use this fuction. but, base situation is drop=TRUE, This can extract pure things if it is not list and demension is under 2.

    It is convenient but dangerous because it can make unpreditable error.

    Also, I introduced is. fuction before, but I'd like add more details.

    We can use this fuction like these. 

    1. is.numeric(type)

    2. is.matrix(data structure) 

    3. is.na( special value)

    In is., it can receive only one data sturcture. So is.matrix result -> 1 length logical vector.

    is.numeric , is. na -> analyze inside of that, and make logical vector. 

    x <- c("a","b","c","d","e","f")

    x[1] "a"

    x[-1] : except x[1] -> "b","c","d","e","f"

    length(x) -> length..

    x[length(x)] "f"

    x=="c" -> "c" (char vector) size is extended same with x length. So c("c","c","c","c","c","c")

    And After logcial calculation, it will be (F,F,T,F,F,F)

    And the x[x=="c] -> "c" (just print true index)

    y<-c(1,2,3,4,5)

    y[y>2 & y<4] -> 3

    x[1,] -> want to print all row=1 value

    if df is dataframe, df$foo -> print pure $foo data (combine them with one data structure)

    df$foo is also vector list etc. So we can do like this -> df$foo[3]...

    a<-c(1,2,3), b<-matrix(1:6,2,3)  l<- list(a,b)

    l[1] -> just list.

    l[[1]] -> vector

    l[2] -> just length 1 list

    l[[2]] -> matrix

    All data structure's length can be 0. such as integer(0) means the integer vector (length=0) it exists certainly. it has header.

    But, it can be calcualted with other data sturcture whose length is over 0. 

    ex) integer(0) + c(1,2,3) (numeric ) -> numeric(0), vector extension is not occured.

    If you want to delete na value, you can do like this.

    which fuction is to indicate the TRUE value's index through integer vector.

    is.na(df$age) ->we can make logical vector (T: na)

    which(is.na(df$age)) -> make the integer index or TRUE.

    So, we can do like this df(-which(is.na(df$age)),) 


    

    
    

    

    

    


    










    

    

    
        

        

    

    

    

    

    

    

    
