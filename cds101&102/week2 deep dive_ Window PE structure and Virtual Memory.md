## PE structure

    PE structure is a formal file form for .exe, .dll, .sys.

    They are main file for executing window. Kernel is also .exe(Ntoskrnl.exe).

    .exe is executing file. .dll is dynmaic linking file. .sys is driver.

    There are 3 structure in that. PE header contains introduction information and virtual address they want.

    Section header contains each section's introduction(size, location etc.)

    Last, Section body. there are 6 types in section.

    text : a main code. we can confirm Virtual address in text through relocation and linking.

    .data, .bss, rsrc : many kinds of data and image files etc. text use these through Virtual Address pointer.

    .reloc : if it is impossbile to contain this file in wanting virtual address mentioned in header,

             They show us the context which I have to relocate.


    .rdata : IAT, ILT, import directory , ENT, EOT, EAT (for dynmaic linking.)

    In text, there are address for iat. Iat will contain virtual address they want to move.(to other file ex:.dll)

    In beginning condition, IAT contains name of fuction they want to link. ILT is just copy version for beginning. 

    And, import directory means Where the fuction they hope to link is.( a.dll etc)

    So, Kernel wants to link. and They find export table of .dll etc.

    ENT is just a table of fuction name. And we can find the Relative Address of fuction with EAT.(Eot uses for middle stage for finding.)

    And we record the virtual address of fuction starting location in IAT changing the Relative Address of fuction to virtual address.

## Virtual Memory

    I will write the procedure of virtual memory with the computer booting procedure.

    After turning on computer, firmware executes for going to next step. Now, it is just real mode. (Cpu mode which doesn't use MMU.)

    Firmware executes bootloader, and bootloader want to execute kernel. (ntoskrnl.exe) So, they just load kernel in the location they want in Header.

    But it is not virtual address. it is just real address. And bootloader finds pc location for starting. 

    Kernel starts to do dynmaic link with .dll and .sys through import and export table. Also, kernel make mapping table for indicating mapping between 

    virtual address and real address. After all linking and mapping table is done, kernel turns on MMU.

    The most important thing is ntoskrnl.exe, .dll and .sys can do linking each other through import and export table. 

    When ntoskrnl.exe make mapping table, they just include all things (.dll. .sys) in its own mapping table. 

    Furthermore, If kernel want to read some files, they just make new virtual memory mapping for the new files and

    After using it, delete it. Also, the ram-uploaded file such as .dll .sys usually never go back to HDD different with other files during computer turn on time.

    After all, Kernel change the mode to Virtual mode and they just remember starting address of mapping table and they record it in CR3 register when calculating.

    Now, we will use usual process such as chrome.exe... First, they upload some files of chrome in kernel and check the pc location.

    All files in window is divided into clusters(4kb). and The file also exists in HDD as 4kb. So, kernel just upload 4 kb which has pc entry point.

    Also, they make mapping table but, the real address is not in RAM. 

    MMU is in the CPU. the rold is just to change virtaul address to real address checking mapping table. But, if it is in HDD. they make page-fault interrupt.

    Through it, kernel's isr code runs. they load 4kb clusters in RAM and change the mapping table. Also, they do dynamic linking through import/export table.

    The most misunderstanding thing is that many people think they just upload all chrome.exe in same time per cluster.
    
    but it is wrong. Although kernel file load to RAM in same time per cluster, user file is different. they just upload files per 4kb only if they need. 
    
    it is same with .dll. if the file is uploaded first on RAM, they do dynamic linking. From next times, they don't need to do linking anymore.

    Although .dll or.exe is back to HDD, they first change the mapping table context to 0. and if they want to use, MMU occurs interrupt. 
    
    And, they just load 4kb on RAM and change the mapping table value. User file uses virtual address so gradually and effectively.

    all files including .dll .txt, .jpg etc are gradually uploaded per 4kb, moved to HDD per 4kb if RAM is full, and come back if it is needed.

    The 4kb unit is independent. they just moved between RAM and HDD. Also, window usually use HDD with three section. File table, File store,

    Virtual Memory back up store. Kernel back up files in Virtual memory back up store to prevent data destorying.

    User program make mapping table with kernel mapping table. It is for efficiency. Kernel just can use their mapping table without changing CR3 register.

    Also, user program's mapping table contains all linked thing's virtual address of user program such as .dll 
    
    and also contains uploaded file they want to use such as .txt file etc. 
    
    Furthermore, many files can use one .dll and kernel manages it to change mapping table when page fault interrupt.

    In cpu, there are two rings. Ring 0 : Kernel mode Ring 3: user mode. 

    User programs can not change the rings because ntoskrnl.exe first occupy ring 0 mode when turning on Computer.

    Changing the ring mode from 3->0 is impossible due to CPU sturcture. 

    If they want to access hardware, Interupt occured and the process is delected due to ISR code.

    The only way for accessing hardware, it is system call. it is just request. and Kernel do it instead of user process.

    Also thanks to virtual memories, we can protect their own process from other process.

    Due to virtual memoires, they can not access our process's real address.

    the address is just changed due to mapping table. it is one of the good things for virtual memories.












    




    






    




    
    

    















    

    
