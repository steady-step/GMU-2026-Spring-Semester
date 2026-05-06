# CDS101 week5

    In R markdown, yaml can use not only yaml grammer but also latex,markdown, r inline code.

    Also, we can insert yaml code in the middle of r markdown through --- ---.

    histogram vs bar graph

    histogram's x axis is number, but bargrah's one is independent character.

    So, there are no distance between histogram but bar graph has distance.

    Y-axis is just number(>=0)

    Y-axis can become not only number but also ratio etc.

    is.na -> make logical vector based on whether the data is na or not.

    which -> make number vector which contains the address of TRUE.

    ex) which(is.na(df$age))

    we can remove rows which have na.

    d <- which(is.na(df$age))

    new <= df[-d,]

    In function, arguments have order. but, if we wrtie the specific name, we don't need to keep order.

    rep : make vector more repeated one.

    rep(data,times,length.out,each)

    First, each is length 1 vector, and it extend each value with the number of each arguments.

    Times -> if the length is 1, just extend the result of each with the number of times.

             if the length is same with original data, just extend each data with the number of each element of times.

    length out -> make final result. if the result is bigger than length out value, cut it.

                  if it is smaller than length out value, extend it.


    ex) rep(c(1,2,3),times=2,length.out=10,each=2)


    first, through each arguemnt, it becomes c(1,1,2,2,3,3)

    second, times is length 1 vector so, it becomes c(1,1,2,2,3,3,1,1,2,2,3,3)

    Last, as length.out is 10, cut it. c(1,1,2,2,3,3,1,1,2,2) -> result

    r Arithmetic Operator : +,-,*,/,(^,**), %/%(quotient), %%(reminder)

    %*% -> matrix multiplication

    getwd() -> print recent project's directory

    package is in package folder, but if we want to use files such as a.txt,

    there are two ways.

    1. move a.txt to recent project directory and call it through file name.extension

    2. use specific address if it is window, we can get it in file address and we should change all \ to /.

    setwd() -> change recent project directory(folder)

    read.table -> read files and change to dataframe.

    we can read it if it is separated data through comma tab etc.

    read.table(data,header,sep)

    base condition is header=FALSE. but if we write header=TRUE, first row becomes colnames.

    sep is separation for dividing data. it can be anything. "" (empty space), " " (space 1), "," ->csv, "\t" ->tab")

    ex) read.table("a.txt",header=TRUE, sep="")

    read.csv -> csv only csv means comma separated value (data is divided into comma)

    read_xlsx, read.xlsx -> excel data. it is private package. (read.table, read.csv is basic function.)

    read.xlsx requires java program.

    head(data) -> the number of basic printing row is 6.

    head(data,3) -> print the top 3 rows.

    head(data,-3) -> exclude the bottom 3 rows.

    tails(data) -> the number of basic prining row is 6.

    tails(data,3) -> print the bottom 3 rows.

    tails(data,-3) -> exclude the top 3 rows.

    [] -> original form

    [[]] -> previous form when making dataframe etc.

    summary() -> print the summmary of dataset. we can analyze all data sturcture (vector,matrix etc)

    summary function print each column's data if it is matrix or dataframe.

    if it is not, it just print all things at once.

    if A is dataframe, summary(A)

    result

    min, median, mean,max, 1st Qu(bottom 25), 3rd Qu(bottom 75) for each column

    if accurate 1st and 3rd Qu doesn't exist, we calculate value for printing.

    colnames can not only reading but also writing.

    colnames(a)[1]<-"a" -> first colnames is changed by this function.

    $ can also add new column like mutate

    a$c <- a+b

    (new c column is made)

    length 1 vector can omit c().

    

















    

    







    

    

    

    




    



    
