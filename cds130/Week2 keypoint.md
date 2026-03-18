# Week2 keypoint

## basic theory

    .m -> markdown file extension.
    
    markdown file name -> only alphabet + number + _ . Also, we should start the file name only with alphabet.

    other symbols are not admitted. (! etc) Capital letter and small letter are separated.

    .docx -> word file extension.

    .pdf -> pdf file extension.

    folder = directory

    syntax : a grammer for making sentence combining word. (it is also used in programming language!)

    Base 10 -> each digit is range from 0 ~9. so Base 2 -> each digit is 0 or 1.

    1 bit -> 0 or 1, 1 byte = 8 bits, 1 word = 32 bits

    Computer only use bits considering the sturcture of logic gate.

    N bits can make 2^n patterns. (ex: 8bits -> 256 signals)

    it is also used for making a color bits.

    Ascii code -> A code for indicating letter. it is made up of 7 bits. and it can indicate 128 letters.

    Extended ascii code -> 8 bits ->256 letters.

    Unicode -> Main way for indicating letters now. 16 bits. 

    1 kb = 2^10 byte. 1MB = 2^20 BYTE. 1GB= 2^30 BYTE.

    

## Basic of Matlab

    Matlab is simillar with R. this language doesn't have exclusive data. The minimum unit is array. (In R, it is vector)

    There are some kinds of arrays.(Numeric, char, string etc). Array is one dimension or two dimension. They are composed of same data type like vector. 

    We make array like this -> [1,2,3;4,5,6] it is numeirc array. , means we'd like to extend data in one dimension. And, ; means we'd like to change the line.

    Array can be one or two dimensions. Also, there are any integer types in matlab. 3, pie, nan and infintiy are also consdiered double type and they are  calculated.

    by CPU logic gate considering the unique data type. (NAN, infinity etc) Also, we make char array liek this -> ['Hello','a'] they are not string. So, the letters 

    are saved as each letter. and they can be calcuated with unicode with numeirc. Finally, we can make string array like this -> ["Hello","ABC"]. They are string.

    So, they can not be calculated as unicode. they cna just put together with themselves. (EX: HelloABC), Also, the most important thing is we should match 

    the number of columns and rows for making arrays. it is essential. And they can caculate each other with automatic type conversion similar with R.

    Also, there are three bigger types for convience. cell array is defined like this. -> { "APPLE", [1,2,3]} it is similar with usual array. But, it can contain

    all kinds of data types(including cell, struct, table etc) and we use {} this icon. Struct can be defined like this -> a.name = "k". We can just write 

    like this. After all, we can call a.name... Also, it is used as 2 dimension -> a(2,3).name-> if we type this, .name is created in (2,3) and also

    2 dimension arrays (2X3) and .name is all created in all 6 sections. Last, Table. We can make columns data with any 6 data types. and type like this

    table(~,~,~) ~ is data types for each columns. 

    Also, disp means print. so we can use this fuction like this disp('Hello world') we can print 'Hello world' without using disp. But, if we don't use

    disp, variable name is included.(If variable doesn't exist, ans is printed).

    variable name can be made by rules similar with file names. (alphabet and number, _ only, first letter is alphabet)

    we can make variable like this -> a=5, d=3, b=d b=b+1

    ; means that it prohibit printing the return value if it is used at the last of the line. but In the disp, letter is printed becuase disp is not related to

    return value. Also, the sequense of the calucating is like this -> () <inside ->outside> -> ^ -> * / -> + -( if the sequense is same, calculate left to right)

    Also, there are many fuctions. ex) pie(print pie), sin(x), cos(x), sqrt(x)9root x), exp(x) (e^x), logx(ln x), log10(x), mod(x,y) (remainder), abs(x) (|x|).

    








    


























    
  
