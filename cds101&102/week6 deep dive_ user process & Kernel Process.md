## Week 6 deep dive (User process vs Kernel process)

    CPU -> real mode -> virtual mode(ring0 vs ring3)

    First, before entrying ring 0, kernel make mapping table of kernel.

    Also, kernel remember its start point(real address) for using it on CR3 register.

    After this process, for making user's process, we need three steps.

    1 Make that user process's mapping table. (it contains not only user one but also kernel one)

       -> We don't need to change CR3 point when we face interrupt or system call.

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

    In Kernel, it can edit and read anything theoretically through making mapping table and editing HDD.

    But, kernel's safe system (Preventing not to delete Kernel, edit kernel etc.)

    So, Kernel's mapping table also has write bit so that it is not changed.

    If Kernel trys to change it -> interrupt(although it is already ring 0)

    Theoretically it is possible through changing mapping table, 

    but OS bring up the blue scrren mainly.

    Process in window -> only .exe

    If kernel add files(such as a.sys) in their virtual address,

    virtaul address of each user process's mapping table also needs to change.

    Bwt, OS uses key point.

    Mapping table is developed so that it can find original kernel mapping table

    without copying it whenver we make user mapping table.

    So, if we just change kernel mapping table only once, the problem is resolved.

    IPC or giving data as the result of system call 

      1 IPC : ex) Mapping shared memory space simultaneouly at a process and b process's virtaul mapping table

                  for communicating and saving their own privacy.

      2 system call result -> Mainly, assign new virtual address space for giving result.

    Theoretically, it can change or read process's code, but it is restricted usually.


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

    



   

















