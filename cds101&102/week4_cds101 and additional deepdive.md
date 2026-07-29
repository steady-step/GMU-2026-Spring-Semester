# CDS101 week4

    is.na -> make logical vector based on whether the data is na or not.

    which -> make number vector which contains the address of TRUE.

    we can remove rows which have na like this.

    ex) d<- which(is.na(df$age))

        new <- df[-d,]

    rep : the function which makes vector more repeated 

    r Arithmetic Operator : +,-,*,/,(^,**), %/%(quotient), %%(reminder)

    getwd() -> print recent project's directory

    package is in package folder, but if we want to use files such as a.txt,

    there are two ways.

    setwd() -> change recent project directory(folder) -> if using window, we should change the address \ to /.

    read.table -> read files and change to dataframe.

    read.csv -> csv only csv means comma separated value (data is divided into comma)

    read_xlsx, read.xlsx -> excel data. it is private package. (read.table, read.csv is basic function)

    head(data) -> the number of basic printing row is 6.

    head(data,3) -> print the top 3 rows.

    head(data,-3) -> exclude the bottom 3 rows.

    tail(data) -> the number of basic prining row is 6.

    tail(data,3) -> print the bottom 3 rows.

    tail(data,-3) -> exclude the top 3 rows.

    summary() -> print the summmary of dataset. we can analyze all data sturcture (vector,matrix etc)

    result

    min, median, mean,max, 1st Qu(bottom 25), 3rd Qu(bottom 75) for each column

    select(data,a:b) -> we can use : specially in dplyr for making range of colnames.

    arrange -> arrange data through character or number (Ascending order or Descending order)

    arrange(data,col1,col2) -> first arrange to col1, and next arranage to col2.

    arrange(desc(col1)) -> descending order

    when we use sum or mean etc. na.rm is basically FALSE.

    but if we want to exclude na when calculating, we set it to TRUE.

    ex) mean(data,na.rm=TRUE)

    Also, if you want to delete group attribute after using summaraize,

    we can use like this -> summrize(data,a=,b=,.groups=drop)

    pivot_wider -> tidyr package (we can call it through calling tidyverse).

    pivot means central axis but, in basektball, pivoting means turning our body making one legs as pivot.

    So, pivot in data science is first, fix other column, second, turn the data.

    we can use like this -> pivot_wider(data,names_from=col1,values_from=col2)

    result -> col1's value becomes new column name and col2 becomes that column's value.

## libary and package

    R is interpreting language. So, r engine uses package everytime they execute programs.

    When we analyze package folder, there are in libary folder. So we call the folder which contains all package folder as library.

    Also, in libary folder, there are own package folders. in package folders, there are files for executing. 
    
    (also it contains some lists of other packages which they want to upload simulatenouly with this package.

    So, package is book. and libary is bookshelf.

    but, in C, the linking machine code called as library. it doesn't mean bookshelf folder.

    library(a) -> upload all a package code and save it. We can use that package's code whenever you want to execute.

    a::book() -> use book function of a package. r engince just find only a function code (not upload all package) and doesnt' save it.

    So, if we want to use it again, we also should use a:: again.

    tidyverse() -> it contains their own function but the main purpose is to upload other related package.

    %>%(pipe) is also from other package. but tidyverse call another package which contains %>% for convience.

    |> -> base r symbol. This symbol is developed as pipe has gotten popularity.
    
    the role is same with pipe.

    Package list which is uploaded by tidyverse

    readr -> upload external file. (ex:read_csv)

    tidyr -> data reshaping. (ex: pivot_wider..)

    dplyr -> data processing and wrangling. (ex: mutate,filter, summarzie etc.)

    ggplot2 -> data visualization

    

    

    

    

    
    

    

    

    



    





    

    

















    

    







    

    

    

    




    



    
