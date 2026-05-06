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

    length.out -> make final result. if the result is bigger than length out value, cut it.

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

    tail(data) -> the number of basic prining row is 6.

    tail(data,3) -> print the bottom 3 rows.

    tail(data,-3) -> exclude the top 3 rows.

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

    tidyverse <- we can use other package(ggplot2,dplyr etc) through calling this.

    read_csv(function from private package)

    select(data,a:b) -> we can use : specially in dplyr for making range of colnames.

    arrange -> arrnage data through character or number (Ascending order or Descending order)

    arrange(data,col1,col2) -> first arrange to col1, and next arrnage to col2.

    arrange(desc(col1)) -> descending order

    when we use sum or mean etc. na.rm is basically FALSE.

    but if we want to exclude na when calculating, we set it to TRUE.

    ex) mean(data,na.rm=TRUE)

    summraize(also we can use it to summraise) has .groups argument.

    Basic condition is "drop_last"

    it means we just delete only last group of previous one in this new dataframe.

    if we want to delete it, we can use like this -> .groups="drop"

    .groups="keep" -> just keep,

    .groups="rowwise" -> make all row as each group.

    pivot_wider -> tidyr package (we can call it through calling tidyverse), it is only for dataframe.

    pivot means central axis but, in basektball, pivoting means turning our body making one legs as pivot.

    So, pivot in data science is first, fix other column, second, turn the data.

    pivot_wider(data,names_from,values_from)

    names_from is columns where we want to change its value through colnames.

    such as a column has 2000,2001,2002,2003.... 2000, 2001, 2002, 2003 becomes new column next to fixed column.

    second, values_from is data which we want to fill in new column.

    so, function fill the blanks considering fixed column. many data may be na as the value doesn't exist.

    also, if the value is overlapped in same blank, the column which has overlapped blank becomes list for making it one element.

    * (list(c(1,2)) has only one element.

    if the number of names_from column is over 1, the overlapped column is made like this -> 2001_james, 2001_cds 2001_mason 2002_usa

    also, if the number of values_from column is over 1, also, the overlapped column is made like this -> data1_2001_james....

    ex) pivot_wider(data,names_from=a,values_from=b)

    rownames, colnames is originally character (colnames vector's type is character)

    if we use colnames in [], we can use it through "" or ``.

    behind of $, "" and `` are optional, but if the colnames is number(ex:100) we should use "" or `` as number can not be located behind of $.

    ex) a$"100" a$`100`

    in [[]], "" or `` is essential.

    In most functions located in private package, "" or `` is optional but it is not always true.

    in select function, select(data,2000) (2000 is colnames) doesn't print 2000 columns.

    it just print 2000st column. So, we should use "" or `` 

    ex) select(data,"2000") or select(data,`2000`)

    

    

    



    





    

    

















    

    







    

    

    

    




    



    
