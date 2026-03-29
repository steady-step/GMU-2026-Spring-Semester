# Week3 cds102

## Before entering

    In yaml, pdf_document can be scalar or object. 

    If you use like this -> output : pdf_document , it is scalar. but you type like this-> 

    output:
      pdf_document:
        toc: true      it is object.
        
    In scalar :  integer, numeric, logical, null, pdf_document should not use " " .

    Others recommend to use " " .

    In library folder, there are many package folders. In packgae folders, 

    there are fuction folder, data folder, man folder(desciption for user), description file, namespace file.

    The most important thing is that they can upload other packages simultaneously through description file.

    In description file, there are other packfile names we should upload simultaneouly, and

    In namespace file, there are specific fuction names and data file names which I will use. They exist in currest package folder and

    other package folder which is introduced for description file.

    Also, we can make many file form freely such as .r, .rmd etc. We just make our own forms and store it at hdd.

    Through ntfs, it is stored with unicode.
    

## Grammer

    qplot() -> A fuction for making plot. We can make plot conveniently with this fuction. (Quick plot)

    if the number of variable is 1 -> histogram, 2 -> scatter plot. (Mostly)

    Difference between histogram and bar graph

    Histogram : x axis is number and there are no interval between them. width is essential.

    Bar graph : x axis is mostly character. Mostly, interval exists.

    qplot(x=a,data=b, binwidth=0.5) -> we can make histogram based on x=a(of data=b) and

    the histogram bar is made based on width=0.5.

    qplot(x=a,data=b,binwidth=0.5,fill=d) -> the original histogram + the color is filled based on d.

    Histogram -> Centered? -> Mode...(Mostly)


    Peaks in histogram(Modality) -> increasing ->peak -> decreasing....

    unimodal : one pick in histogram

    bimodal : two picks in histogram

    multimodal : over three picks in histogram

    









    

     
    






    

    
