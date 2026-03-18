# Week2 cds102 (R markdown)

## R markdown structure

    1. YAML : Data Serialization Language. The common language for indicating form of file (ex: title, author, date, form of file(pdf) etc.)

    2. Markdown :  The common language for making document neatly. We can change the style of letter, create table, insert picture etc.

    3. R : We can insert R code in R markdown with result.

    4. LATEX : A common language for writing mathematical signals which don't exist in US keyboard.

### YAML

    First of all, we should code --- on first line. This section is called as YAML header.
    
    The essential part for YAML header is output part for choosing what forms you want. (PDF,WORD,HTML)

    Type like this -> output:    it means that we will select the form of output.(it is attribute)

    There are two options of result. First option is that we type another attribute as sub-attirbute.

    Second one is that we type scalar. Scalar means forms which can not devided into anything.

    There are 5 kinds of scalars : strings, numbers,booleans, NULL, etc.

    Numbers, Booelans, NULL, Numbers, documents type never use " " . Other recommend to use " ".

    If, there is only one sub-scalar we can type like this -> output: pdf_document (output+:+space 1 + scalar)

    But, originally, the basic grammer is to type like this... 

    output:     (output+:+enter+space2)
      pdf_document:
        toc:TRUE

    ["float"] : List, th combination of scalar.
    Also, we can add yaml code in the middle. 


### Markdown

    # title : it can make title... if we add the number of # the size of title is decreased.

    **abc** : Make bold letter. *abc* : Make Italics.

    - abc : Unordered list    1. abc : Ordered list.

    <Space in Markdown>

    Space in the middle of word -> it is only considered as one space.

    Behind of #, -. 1.  -> activate the fuction.

    Space 2+ enter at the end of the sentence -> line break

    Space 4+ at the start of the sentence -> it is considered as code. The markdown signal can be shown and automatic line break is not applied. 
                                             Also, all space can be shown.

    Space 2~4 at the list -> Make sub list.

    Under 4 at the start of the setence -> Ignored.

    <Table>

    First of all, write |    |    |    |  for making first raw, and write letter. | a | b |  c |

    Second, write second raw like this.. |  |   |   | this raw means sort of the columns.

    you can write * over the number of 3 for sorting. and write :.  *** and :*** means left sorted, ***: means right sorted, :***:means center sorted.

    ex) | ***** |  ***: | :***: | (You can write * over 3) it means left, right, center sort each.

    and You can write |  |  |  | for making other raws like first raw (ex:  |hello |  hi  | nice  | )

    Also, for making captions of table you can write Table : title behind the table. (There should be no codes between them.)

    
    <Others>

    For line breaking, there are 3 ways.

     1. <br> (1 line)

     2. space 2 & enter (1 line)

     3. enter 2+ -> seperating paragraph. (2 line)


    For inserting picture : ![caption](file.png)


### R code

    For inserting R code, type like this

    ```{r}
      ~code

    ```

    you can see code and result when changing this to pdf.

    also, there are two key points.

    1. we can make a name of this chunk. ```{r setup}

    2. we can add some setting ```{r, warning FALSE, include=FALSE}

     warning FALSE means hiding warning message. and include=FALSE means hiding all result and code in PDF HTML etc.


### LATEX

    For using LATEX, TYPE $ $ . and we should type LATEX code between them.

    we can type x=10.. it automatically change font of x.

    if we want to write square, x^n, subscirpt -> x_n 

    If the location is changed different with usual keyboard such as suqare, it only admit one letter.
     
    So, when we want to write x^10, 10 is two letter. so we should type like this. $x^{10}$.

    {} is used for combining a number of letter.

    Also, if the signals don't exist on keyboard, we should use \.

    fraction a/b -> type like this. \frac a b,  alpha(greek alphabet) -> \alpha... 

    sqrt a^2+b^2 -> \sqrt {a^2+b^2} 

*** Others

    Unicode -> Current code for using cha

    
    
    

    














    
    
   








    

  
    
