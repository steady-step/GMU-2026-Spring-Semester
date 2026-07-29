## Week 6 deep dive (User process vs Kernel process)

    CPU -> real mode -> virtual mode(ring0 vs ring3)

    First, before entrying ring 0, kernel make mapping table of kernel.

    Also, kernel remember its start point(real address) for using it on CR3 register.

    After this process, for making user's process, we need three steps.

    1 Make that user process's mapping table. (it makes mapping table which can find also kernel mapping table through tracking)

       -> We don't need to change CR3 point when we face interrupt or system call whenever computer mode is changed to kernel mode.

       -> Kernel should also remember its real start point address for CR3 register.

    2 Loading user program and set PC.

    3 Change mode(Ring 0->Ring 3)

    If interrupt or system call occurs, register's address automatically changes for starting ISR, 

    and mode changes to Ring 0.

    And we execute kernel code without changing CR3 register value.

    Also, in same virtual memory range(user<->user), user process can access files there.

    But, request to kernel for registering files is essential.

       Ex) a.exe -> read v.txt ( v.txt -> mapping at a's virtual address range through request to kernel)

    Furthermore, in mapping table, access signial is in that.

    if Write bit is not allowed, although a.exe want to write on v.txt, MMU error -> Ring 0 -> Kernel execution.

    Process in window -> only .exe
    
    Virtual Kernel address is much higher than user process's one.


    *** Memory location key point ***


    memory 

    1. mapping table space (we should remember start point for cr3 register)

    2. Virtaul address -> in mapping table real address value result, the index belongs to mapping table(real address) is excluded.

        2-1. memery address

            2-1-1. each user's virtaul address

            2-1-2. Kernel virtual address

        2-2.Rom

        2-3. MMIO

        (2-2 and 2-3 is also in mapping table, but its virtual address usually matches with real address.)

        (They are not memomry. they just registers and rom)


    3. ISR -> it executes based on virtual address.

       internal interrupt -> it doesn't need to view IVT.

       By the kinds of each interrupt, the address is automatically changed by HW, and we should make ISR code in that specific virtual address.

       System call & I/O interrupt -> We can control its ISR code location through changing IVT.

       IVT table location is already fixed, and through filling the ivt table,

       the start point of ISR code is fixed.

       Kernel just write the isr code based on automatic address start point our-made IVT table start point.

    



   

















