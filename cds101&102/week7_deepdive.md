# Week 7 Deep dive

Following week 6 deep dive,

I will deal with Computer structure especially based on CPU, ISR, and  transistor.

     First, we can classfy interrupt type with these 3.

     1. external ISR -> made by I/O apic

     2. internal interrupt(timer etc.)
     
     3. System Call

     2 is created by local APIC, and 3 is just made by CPU command.

     As I said before, the CPU which will perfrom each i/o interrupt signal is chosen by i/o apic.

     All cpus have their own stacks which contain the process context.

     It can not be intervened by other CPUs.

     If mouse interrupt is perforemd by CPU 7, CPU 7 makes signal in kernel code.( ex at CPU 5)

     and when CPU 5 read ISR code, the CPU can know it should create new process.

     Through this process, process is created.

     Timer interrupt just changes process and it can not create new process.

     IPI can give signals to other CPUs.

     Except these, other internal interrupt just performs usual exception.

     System call can not only create process and change process but also resolve exception problem.

     But this is not created by APIC. it is just created by user program and own CPU command. (Window : syscall())


## Other point

    There is only one controller (such as SATA) per each type in computer.

    Memory controller doesn't have cpu, rom, ram and firmware.

    It is just logic gate, and it is just located between CPU and RAM.

    Also, it exists in every CPU.

    If cpu requests for accessing to memory, after arbitar is allowed,

    the request is performed, and finish siginal is sent to CPU.

    In recent computer, the most of circuit tends to be located inside CPU.

    Also, multiple CPU system has a limitation as many CPU can not use extenal bus simulatenously

    as the bus is connected each other.

    So, the situation when CPU 1 sends data to SATA controller and CPU 2 sends data to RAM simulatenously is impossible.

    This is controlled by Arbitar.

    But, considering the situation of usign external bus command, using multiple CPU is more efficient than single CPU.

    Transistor has two roles mostly in computer.

    1. binary calucation.

    2. voltage amplification using 2 not gates.




    

    

    








     
















     










     
