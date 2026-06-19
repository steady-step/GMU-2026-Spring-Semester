# Week 5 deep dive

## CPU structure etc.

    CPU is just composed of many logic gate.

    The logic gate makes the specific command and CPU mode.

    First, in CPU, there are 3 elements. CU, alu and registers.

    First CU is composed of Sequential Circuit and Combinational Circuit.

    This element is the main component of CPU.

    Tri state buffer is circuit which can make three condition. (0,1,Z)

    if enable=1, input : 0, output:0 , input: 1, ouput: 1

    if enable=0, input : 0, output: Z, input: 1, output:Z

    1 means connecting with VCC(+), 0 means connecting with gnd-, and Z means cutting off V.

    It can protect data and circuit through cutting off V. 

    We can classfiy bus in two groups.

    1. external bus -> after receiving handshake and interrupt signals, it controlls tri-state buffers each other.

    2. internal bus -> Control unit is king. it controlls tri state buffers in cpu.

    (CU just communicate with ALU and register with internal bus.)

    First, register is just combination of flip-flop. So, each flip-flop(1bit) connects with internal bus(1bit) through input point and output point.

    And, CU controlls them through changing tri-state buffer's enable bit and register's condition bit.

    For communicating with ALU, CU uses registers also.

    For example, if we want to multiply two datas, we use R1,R2 registers.

    First, CU inserts data in R1 and moves the data to ALU through opening tri-state buffer.

    Second, Also, we use R2 registers like this and gives signal(sum) to ALU.

    ALU is just composed of combinational gate, So, after 1 clock, the calculation is done, and We also open tri-sate buffer for getting result.

    First, get a result and second, get a flag bit in next clock.

    This is just one calculation. To mulitiply, we should calculate many times for finishing one commmand.

    When using external bus, it is same with internal bus. But, they use handshakes and interrupt each other.

    DMA is Direct memory access. And recently, it is occured by each controllers. They have their own DMA registers. And use it.

    <Memory -> controller>

    First, CPU just informs specific address, count number, and control singal to controller through usual bus.

    Controller saves it in their registers, and if it is ready, they ask unlocking of tri-state buffer to ram circuit.

    In controller, they have four registers about DMA. address, data, control, and count. The special thing is count.

    DMA is repeating until the count will be 0. (and if it is 32 bit computer, the each unit per loading is 32bits)

    If the tri-state buffer is unlocking, they use dma address bus, data bus and control bus for loading them.

    the process is dominated by them until it it done because dma circuit is shared circuit with other contorllers.

    The data which they load is continious in RAM. And after finishing them, they call interrupt, and the next step is occured.

    <Controller -> Memory>

    It is simillar with previous one. As cpu already knows the size of data, cpu finds the continious parts on RAM.

    And it is loaded with same process with previous one.

    There are 3 special units in Computers.

    Arbiter controlls the order of asks of that their tri-state buffer is unlock.

    This unit is also just composed of logic gate, and it finally gives the signal which can unlock the tri-state buffer or unlock directly(DMA).

    APIC controlls the order of Interrupt and select what CPU is assinged to this ISR signal.

    This is also composed of just logic gate, and The detailed concept will introduce in multiple CPU steps.

    Timer is to make timer-interrupt, and it is also assigned with each CPU.

    This interrupt has role to change process periodically. 

    This 3 module can change the mode through MMIO access.

    Interrupt is composed of software interrupt, zero division interrupt, external line interrupt etc.

    Except external line interrupt, they don't use APIC. In cpu, it just make interrupt, and occur stack back-up and automatic address change.

    After finishing that, previous condition is recovred due to stack-backup. But, external line uses APIC. APIC controls the order of that, 

    and make signals on their line to CPU. Their processes are different. 

    Now, I will introduce multiple CPU.

    Multiple is possible and it is used for many computers.

    Presenting the process, in the early stage, Top CPU exists. 

    Top CPU executes Firm ware automatically (HW) and bootloader and kernel(SW)

    But, After uploading kernel, Top CPU turns on their timer and assignes CPU number for each ISR line for efficiency through MMIO.

    Through this, if MMIO line 35 is called, and CPU 5 is assigned, CPU 5 just gives this. Other CPU ignores.

    And, Top CPU makes interrupt for reseting. After this, the address is formed, and through this, CPU can fill their registers.

    Next, Turn on MMU and Timer... Timer interrupt starts. and If the timer interrupt occured, the data is back up on RAM, and

    ISR code is executed. Schedular can controll schedule through given CPU number information. 
    

## Real process in CPU below abstraction


    In CPU, there are mechanical processes which we can't know if we only use upper programs.

    First, there are four processes. Fetch -> Decode -> Execute -> Write Back.

    Although write back doesn't exist in some commands, it should occupy as a process for consistency.

    Recently, many cpu use pipelining. It means executing four processes above them simultaneously.

    But, all process should be done for going to the next step.

    In computer, there are two command types. RISC, CISC.

    RISC is simple commands. They have same-size command. and the form is also similar with each other.

    So time-delay is few.

    But CISC is not simple commands. They have different size command, and the form & executing style are different each other.

    This makes time-delay than RISC.

    Also, many data structure such as Queue, Tree, Graph etc don't exist really in RAM.

    They just abstracted theory for computing users.

    When we analyze PE file, there are just many commands based on their registers, memory address etc.

    There are not graph in RAM.

    Computer command is composed of opcode and operand. Opcode means just the command type, and operand is factor.

    In CISC, operand can be diverse forms. and operand can be multitude. (the numbeer of operand can be 1,2,3...)

    So, the decoding circuit needs in decoding process. 

    Although there are many commands in CPU, but they are mostly related to low-level command(register,memory address etc.) Not advanced command.

    The only thing which CPU reflects for data structure is stack. There are commands in CPU (push, pop) for adding and deleting data in stack.

    But, this is also just composed of RAM and register called stack pointer. In stack pointer, CPU just save the top address. 

    And we change that per 4(if the computer is 32 bits computer) if the push and pop is occured.

    But, this is just register! not real stack! So we can extract bottom data immediately with another way.

    It is easy. First, find the data address which you want to find, and just extract them. And lastly, if you change the stack pointer value

    considering changed one, it is done! Finally, I want to emphasize that computer base is just simple than preoccupation. Thank you.

    






    



    















    

    

    

    
