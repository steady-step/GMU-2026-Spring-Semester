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



### Virtual memory , use of packages and communication between processes.

     Virtual memory : allocating virtual memories instead of real memoires. we use mapping tables and mmu. 

     When we use chrome.exe, kernel read exe header for finding starting point(pc). And make their own mapping table.

     (virtual memoires <->real memoires) But now, they exists on hdd. so we record the clusters. 

     For finding the real address, we should know cr3 register(the start address of the table) and virtual address.

     After finding the real address, we want to start process but interrupt occured (it exists on hdd!)

     Cluster is 4kb. So we upload 4 kb on ram. Also, we should relocate the address and do dynamic linking. (.dll)

     .dll is used as virtual memory skills. First of all, Be uploaded 4 kb and relocated by kernel. Also, it is recorded on chrome.exe table.

     And if the ram is full, it is gone back to HDD. and if it is back, it is relocated again by kernel. 

     It is same with chrome.exe! chrome is uploaded with 4kb(cluster). and if the ram is full, it is gone back to RAM.

     And if they want to back due to command, they will be back, and the addresses are relocated.

     Also, we are misunderstanding about uploaded file. such as a.txt on chrome. it is not uploaded on chrome.exe!

     It it just included on chorome.exe mapping table! and chrome.exe just get a virtual address for getting it.


    Also, there are some processes in OS. they can not intervene each other. Parent process<->Child process are also differnet process. 

    But they can commuicate only through admitted path such as pipe. They can not change their own data.

    Also, other processes only communicate through admmited path such as shared memory. 
     




### Others

    Unicode -> Current code for using character instead of ascii code.

    Library : The folder which have all package folder.

    Package : The pre-made data and fuction for using easily in programming language.
              We easily use these fuctions and datas through library(name) in R.

    The process for changing r markdown to result file..

      rmd is just a file. and we need some package for changing this file to reuslt files.

      When we click knit, some package fuction operates through ::, and it is prepared.

      and There are another SW for making PDF etc. So it makes this files to PDF.


    In r studio

     console : the tool for communicating with r.exe... there are some fuctions for controling r studio except calcaulating fuction.

     Terminal : the tool for communicating with OS.

    







     

     

    
    
    

    














    
    
   








    

  
    
