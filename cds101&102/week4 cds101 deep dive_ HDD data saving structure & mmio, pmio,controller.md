# week4 cds101 Deep dive

## HDD data saving sturcture

    In HDD, there are space called as MFT.(about 12.5% of HDD).

    It stores file meta data and folder meta data. Each space for file and folder meta data is 1kb.

    In 1kb, all meta data(file name, file extension, location of each cluster) exists.

    File is stored with the unit of cluster(4kb). and each cluter is scattered.

    For installing .exe or saving .txt etc we need some processes.

    There are two main ways for installing files. first one is through interent and second one is through usb etc.

    If we download it through interent, chrome.exe get the file and use system call for sending them to HDD.

    If you use USB, explorer.exe do that processes. Explorer.exe is the user process which made our window graphic.

    Usually, .exe fild use install another file for downloading.

    If you want to delete the file, kernel just make the program's mft(1kb)'s flag bit to 00 (01 : use, 02 : folder)

    Also, you want to update .txt file on window notepad program, window notepad update their mapping table whenever you type the letter. (Extend .txt file)

    And you click save button, do system call for updating it again.

    .exe file is similar with that. but they themselves can't do that. window prohibit these due to danger.

    Window can know this file is executing through MFT and usual .exe file uses through another update program for updating.

    Kernel can not update if kernel is turned on. So, Window uses bootloader. First, Window downloads new ntoskrnl.exe on another folder.

    It is important. If the same-named file is in another folder, it is ok in Window.
    
    And, when computer is turned on in next booting, bootloader changes it to new version.

    For preventing file damage(computer is suddenly turned off), Window always changes MFT after updating clusters. it prevents file damage.

    But, if the computer is suddenly turend off when making MFT? So we need Log file. We can find log file through MFT entry 2.

    There are 3 information. Original information, Changed information, Adddress of MFT. After turning on the computer, Window check log file.

    if the MFT is different with changed information(original information or broken information), Window changes it to changed version.

## Controller and mmio , pmio

    In computer, there are controllers between CPU and other units.(RAM,ROM,HDD,GPU etc...)

    Between cpu and ram/rom, there are ram and rom controllers. they are connected with addreess bus, data bus, control bus and their registers.

    Also, controller <->ram/rom is coneected with bus and their own circuit around them.

    But, external unit's controllers are different.

    For example, There is a relationship of CPU <-> SATA controller(High speed serial circuit) <-> HDD. 
    
    Contoller and HDD communiate with packets not usual bus through handshakes.

    But, Cpu<-> Controller uses usaul bus(address, data, control) but the way is not same with ram/rom.

    PMIO means the port number is assigned for each controller's register. So, if we write address on addressbus, 

    and data on databus, first the data is written on data register, but the value is written at the register which has specific port number soon.

    Also, if we use control singals with them, CPU can control the controller freely.

    MMIO means the register is also assigned as memory's address. EX) If the possible address is 2^32, 90% : RAM, 9% : ROM, 1% : MMIO Register 1%

    In other words, the registers of controller are assigned as each real address. So, if we use address bus and data bus,

    First it is assigned in data register, but the value is moved to the assigned register soon.

    Also, recent controller has dma function. If cpu gives them specific address and control fuction, they can send data directly. and it is faster than usual way.

    For example, if CPU wants to send data to HDD(64 bit computer), they send the data per 64bits to controller(or DMA), 
    
    and if it becomes 4kb, CPU gives them singal to send data to HDD with packet form. 
    
    After completing that, interrupt is occured.

    If CPU wants to take data from HDD, first they send the signal about HDD for taking that, 
    
    and if it is completed, interrupt is occured, and CPU can take datas through DMA or CPU.

    This process is same with USB and PCle etc.






    

    
