# Week3 cds102

## Grammar

    qplot() -> A fuction for making plot. We can make plot conveniently with this fuction. (Quick plot)

    if the number of variable is 1 -> histogram, 2 -> scatter plot. 

    Difference between histogram and bar graph

    qplot(x=a,data=b, binwidth=0.5) -> we can make histogram based on x=a(of data=b) and

    the histogram bar is made based on width=0.5.

    qplot(x=a,data=b,binwidth=0.5,fill=d) -> the original histogram + fill option(area)

    qplot(x=a,y=b,data=c, facets = ~d) facets -> divide graph into many graphs.

    qplot(x=a,y=b,data=c) -> scatter plot

    analyzing correlation : positive/negative etc.

    analyzing the big shape : we can know the degree of correlation.

    x-> explanatory variable, y-> response variable

    qplot(x=a,y=b,data=c,color=d) -> color option(dot+line)

    qplot(x=a,y=b,data=c,facets=~e) -> make many scatter plots based on e.

    qplot(x=a,y=b,data=c,geom="smooth",method="lm") -> geom: geomatric object (if x and y exist, basic option is point)

    method -> "lm" -> if geom is smooth, the shape type you want. (lm -> linear model)

    qplot(x=a,y=b,data=c,geom=c("smooth","point"),method="lm") -> make point + line.







    

    









    

     
    






    

    
