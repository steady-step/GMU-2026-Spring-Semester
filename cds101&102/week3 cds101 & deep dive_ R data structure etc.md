# Week 3 key points

## Structure of R data structure

    R data struture is composed of header and data. In header, there are length etc, and a pointer for attributes.

    If you go to the pointer address, there are TAG, CAR, AND CBR. TAG means what recent attribute is (dim etc),

    CAR also contains pointer for finding main source about this attribute. For example, I will present names attribute in vector.

    If you go to the pointer address of CAR, there are basic header(length and type) and body. In body, there are also pointers. 

    And the number of the pointer is same with the length of the vector. You can also go to the address through pointer.

    Finally you can find the header(type, length) and the names. We can't know this process when using just R. but R interpreter should use

    so many processes related to pointer. Also, the header in attribute is not same with vector header. You should distinguish these two header.

    It is different. Vector,matrix,array just have a body which contains real information. Factor is also same, but levels is located in attributes.

    Dataframe and lists are different. It is important. In their body, they just have a pointer about that. and We also should find the real informatin through        pointer.

    I will introduce major attributes : names(vector), dim/dimnames(matrix), levels(factor).

    Name means the labels of each element, and dim means dimension of that. dimnames is labels of that.

    Dataframe doesn't have dim, but we can know that indirectly.

    

    

    
