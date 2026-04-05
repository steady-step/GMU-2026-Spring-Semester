# Week 4 cds102 key point

## Misunderstanding point

    qplot -> 1 variable : histogram, 2 variables : scatter plot(filled circle)

    plot -> 1 variable : scatter plot based on index(non-filed circle), 2 variables : scatter plot(non-filled circle)

    plot(matlab) : 1 variable : line graph based on index, 2 variables : line graph.

    ```{r}
    ```     -> In r markdown, it makes r code.

    ```
    ```     -> just make letter like code style (gray box, markdown grammer is not applied, aunotomaic line break is not applied.)

    ` `     -> same with ``` ```

    but, if you type r as first letter in ` `, you can use it as in-line code.

## Grammer

    dplyr package -> it is used for wrangling data frame, and we can also use it through calling tidyverse.

    select -> In dataframe, it can extract specific columns with pure dataframe sturcture.

    select(data,col_name1,col_name2....)

    also, ! or - means extracing columns except that column. ex) select(data,-col3,!b)

    starts_with means extracting columns starting with that. and contains means extracting columns containing with that.

    ex) select(data,starts_with('a')), select(data,contains("p")).

    filter fuction is for extracing specific rows with specific given conditions.

    it should make the result like TRUE/FALSE..

    sturcture is like that.. filter(data,condition1,2,3,...)

    filter(data,m==10,!is.na(d) etc...)

    Fuction uses this condition for checking whether this row will extract.

    if the result is TRUE for specific row, it will be printed.

    %in% is a special operator. the direction(left & right) is so importnat, and vector extension is not occured.

    it is considered TRUE if there are any same data in right vector.

    such as... c(1,2,3) %in% c(3,4,5,6) -> F,F,T becuase 1,2 don't exist in right vector, but 3 exists although they are not same location each other.

    group_by is for making special attributes in data frame. the fuction sturcture is like this : group_by(data,colnames1,2,3,...)

    The fuction classifies each row following colnames. if the colnames 1,2, and 3 exist, fuction first classifies each row following columns1.

    If the column 1 can be classifed with three kinds, it will be made 3 kinds. And, continues same steps with already-made 3-kinds through col2,col3.

    After finishinig, that, there are groups attribute in dataframe.

    Groups attribute is also dataframe, and the columns are composed of each column, and .rows columns.

    .rows columns is a list which has each row location about each group.

    ex) c1 c2   c3     .rows
         A seoul 2  c(1,3,4) means the row which has A at c1 column, seoul at c2 column, 2 at c3 column is 1,3,4 rows.

    summraize fuction is
    













    

