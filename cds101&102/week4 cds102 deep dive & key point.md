# Week 4 cds102 key point

## Confusing points

    qplot -> 1 variable : histogram, 2 variables : scatter plot(filled circle)

    plot -> 1 variable : scatter plot based on index(non-filed circle), 2 variables : scatter plot(non-filled circle)

    plot(matlab) : 1 variable : line graph based on index, 2 variables : line graph.

## Grammer

    dplyr package -> it is used for wrangling data frame, and we can also use it through calling tidyverse.

    select -> In dataframe, it can extract specific columns with pure dataframe sturcture.

    select(data,col_name1,col_name2....)

    also, ! or - means extracting columns except that column. ex) select(data,-col3,!b)

    starts_with means extracting columns starting with that. and contains means extracting columns containing with that.

    ex) select(data,starts_with('a')), select(data,contains("p")).

    when using select function, comma is equals with or for condition.

    Also, we can use & and | only when column names are not included such as starts_with, contains

    ex) select(data,starts_wirh("a")&contains("b")) -> ok

        select(data,column1&column2) -> X

    filter fuction is for extracing specific rows with specific given conditions.

    sturcture is like that.. filter(data,condition1,2,3,...)

    condition structure is column operator condition ( ex) column1 == 3)

    in filter, comma is equal with and for condition.

    Also, we can use & and | in each condtion.

    ex) filter(data,column1==3& column2>5 , column3==5)

    group_by is for making special attributes in data frame. the function sturcture is like this : group_by(data,colnames1,2,3,...)

    when executing this function, attribute is created.

    ex) column1  column2  .rows

          a        b       c(2,3)

          b        c       c(4,5)     -> it means the row's classification by column's value.

    Through these, execution of dplyr package occured per each group's row.

    summarize function is for making user's own summarize.

    it is used like this -> summarize(data,a=, b=) (a,b is new column name)

    ex) summarize(data,a=column1+3,b=column2-column3)

    

    








    
    













    

