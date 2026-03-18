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

    1 bit -> 0 or 1, 1 byte = 4 bits, 1 word = 32 bits

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

    Array can be one or two dimensions. Also, there are any integer types in matlab. 3, pie, nan and infintiy are also consdiered double type and they are calculated

    by CPU logic gate considering the unique data type. (NAN, infinity etc) Also, we make char array liek this -> ['Hello','a'] they are not string. So, the letters 

    are saved as each letter. and they can be calcuated with unicode with numeirc. Finally, we can make string array like this -> ["Hello","ABC"]. They are string.

    So, they can not be calculated as unicode. they cna just put together with themselves. (EX: HelloABC), Also, the most important thing is we should match 

    the number of columns and rows for making arrays. it is essential. And they can caculate each other with automatic type conversion similar with R.

    Also, there are three bigger types for convience. cell array is defined like this. -> { "APPLE", [1,2,3]} it is similar with usual array. But, it can contain

    all kinds of data types(including cell, struct, table etc) and we use {} this icon. Struct can be defined like


























    
  
