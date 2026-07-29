# week4 cds101 Deep dive

## HDD data saving sturcture

    In HDD, there are space called as MFT.(about 12.5% of HDD).

    It stores file meta data and folder meta data. Each space for file and folder meta data is 1kb.

    In 1kb, all meta data(file name, file extension, location of each cluster) exists.

    File is stored with the unit of cluster(4kb). and each cluster is scattered.

    If you want to delete the file, kernel just make the program's mft(1kb)'s flag bit to 00 (01 : use, 02 : folder)

## Controller and mmio , pmio

    In computer, there are controllers between CPU and other units.(HDD,GPU etc...)

    For example, There is a relationship of CPU <-> SATA controller(High speed serial circuit) <-> HDD. 
    
    Contoller and HDD communiate with packets not usual bus through handshakes.

    But, Cpu<-> Controller uses usaul bus(address, data, control) but the way is not same with ram/rom.

    PMIO means the port number is assigned for each controller's register. So, if we write address on addressbus, 

    and data on data bus, first the data is written on data register, but the value is written at the register which has specific port number soon.

    Also, if we use control signals with them, CPU can control the controller freely.

    MMIO means the register is also assigned as memory's address. EX) If the possible address is 2^32, 90% : RAM, 9% : ROM, 1% : MMIO Register 1%

    In other words, the registers of controller are assigned as each real address. So, if we use address bus and data bus,

    First it is assigned in data register, but the value is moved to the assigned register soon.

    Also, recent controller has dma function. If cpu gives them specific address and control function, 
    
    they can send data directly. and it is faster than usual way.

    If CPU wants to take data from HDD, first they send the signal about HDD for taking that, 
    
    and if it is completed, interrupt is occured, and CPU can take datas through DMA or CPU.

    This process is same with USB and PCle etc.





    

    
