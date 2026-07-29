# Week2 cds102 (R markdown)

**Week 1 was just preparation week**

## R markdown structure

    1. YAML : Data Serialization Language. The common language for indicating form of file (ex: title, author, date, form of file(pdf) etc.)

    2. Markdown :  The common language for making document neatly. We can change the style of letter, create table, insert picture etc.

    3. R : We can insert R code in R markdown with result.

    4. LATEX : A common language for writing mathematical signals which don't exist in US keyboard.

### YAML

    For using YAML in R markdown, we should type --- on the first line.

    And YAML is composed of key and value.

    First for using key, we type like this -> key:

    And there are two ways.

    1. scalar

    2. other inner key

    First, when we use scalar, there are three ways.

    1) key: value

    2) key:
         value

    3) key:
         - value1
         - value2

    Second, when use other keys, we type like this.

    key:
      key2: scalar2
      key3: scalar3

    When we type value, using " "  or ' ' is recommended for preventing error message.
    

### Markdown

    # title : it can make title. if we add the number of #, the size of title is decreased.

    **abc** : Make bold letter. *abc* : Make Italics.

    1. abc -> number list

    space x 4 or ` ` or ``` ``` -> make block

    ```{r}
    r code
    ```
    `r ~` r inline code

    <Table>

    First of all, write |    |    |    |  for making first raw, and write letter. | a | b |  c |

    Second, write second raw like this.|  |   |   | this raw means sort of the columns.

    you can write - & : for sorting

    :--- -> L    --- -> M  :---: -> M   ---: -> R

    and You can write |  |  |  | for making other raws like first raw (ex:  |hello |  hi  | nice  | )

    For inserting picture : ![caption](file.png)


### LATEX

    For using LATEX, we can remember five ways easily.

    1. type $ $

    2. if the letter which we want to use is on the key board -> just use it

    3. if it is not -> \function name{}{} ( the number of {} is over 0)

    4. important... if we use superscript or subscript, use ^(super), and _(sub)

       and if the number of letter if over 1, use {}.


### Virtual memory , use of packages and communication between processes.

     Virtual memory : allocating virtual memories instead of real memoires. we use mapping tables and mmu. 

     When we use chrome.exe, kernel read exe header for finding starting point(pc). And make their own mapping table.

     (virtual memoires <->real memoires) But now, they exists on hdd. so we record the clusters. 

     For finding the real address, we should know cr3 register(the start address of the table) and virtual address.

     After finding the real address, we want to start process but interrupt occured (it exists on hdd!)

     Cluster is 4kb. So we upload 4 kb on ram. Also, we should link .dll for original file through iat and eat (window file structure PE)

     .dll is also included as part of the virtual memoires.

     And if the ram is full, it is gone back to HDD. and if it is back, we just change the mapping table.

     It is same with chrome.exe! chrome is uploaded with 4kb(cluster). and if the ram is full, it is gone back to HDD.

     And if they want to back due to command, they will be back, and the mapping table is changed.

     Also, we are misunderstanding about uploaded file. such as a.txt on chrome. it is not uploaded on chrome.exe!

     It it just included as chorome.exe mapping table! and chrome.exe just set a virtual address for getting it.


    Also, there are some processes in OS. they can not intervene each other. Parent process<->Child process are also differnet process. 

    But they can commuicate only through admitted path such as pipe. They can not change their own data.

    Also, other processes only communicate through admmited path such as shared memory. 
     

### Others

    Unicode -> Current code for using character instead of ascii code.

    Library : The folder which have all package folder.

    Package : The pre-made data and function for using easily in programming language.
              We easily use these functions and data through library(name) in R.

    The process for changing r markdown to result file..

      rmd is just a file. and we need some package for changing this file to result files.

      When we click knit, some package function operates through ::, and it is prepared.

      and There are another SW for making PDF etc. So it makes this files to PDF.


    In r studio

     console : the tool for communicating with r.exe... there are even some functions for controlling r studio except calculating fuction.

     Terminal : the tool for communicating with OS.

    







     

     

    
    
    

    














    
    
   








    

  
    
