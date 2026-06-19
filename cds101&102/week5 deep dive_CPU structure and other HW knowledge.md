# Week 5 deep dive

## CPU structure & process

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

    It is located in output circuit. (Not input circuit)

    Because in input circuit, register can ignore all data.

    But, in output circuit, for preventing collusion of voltage, it is essential.

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

    ** For preventing affection of Combinational Circuit by computer bus, register do roles as buffer zone.

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

    This unit is also just composed of logic gate, it is only one in computer, and it doesn't have firmware or mmio.

    Just logic gate.

    APIC controlls the order of Interrupt and select what CPU is assinged to this ISR signal.

    Usually, there are two types. local APIC, i/o APIC. 

    local is for making order of each CPU's interrupt. (per each CPU)

    i/o APIC is to select which of CPUs the isr siginal will be assigned to. (only one)

    ex) ISR 15 -> cpu no.7

    In APIC, there are mmio, but no firmware.

    Timer is to make timer-interrupt, and it is also assigned with each CPU in local APIC.

    This interrupt has role to change process periodically. 

    Timer is also just circuit. It doesn't have any MMIO system or firmware.

    Interupt : external interrupt, internal interrupt, system call.

    Except external line interrupt, they don't use APIC. In cpu, it just make interrupt, and occur stack back-up and automatic address change.

    After finishing that, previous condition is recovred due to stack-backup. But, external line uses APIC. APIC controls the order of that, 

    and make signals on their line to CPU. Their processes are different. 

    Now, I will introduce multiple CPU.

    First, after turning on the computer, top CPU executes.

    It completes kernel setting including mmu mapping table.

    Also, top cpu sets i/o apic and each local apic based on kernel code.

    After this process, it makes signal through its local apic.

    Through this signal, other cpu turns on and changes from real mode to virtual mode based on finished kernel settings.

    First, top CPU starts to make first user process and changes mode to ring3.

    All cpus share kernel code, but we can know the difference per each CPU through command for checking its CPU number when entrying ISR code.

    Usually, through Kernel, all cpu can know what cpu occupies user process and its cr3 point.

    But, each CPU can view their stack for saving context of their all responsible user process.

    It differs based on its cpu number by kernel code.

    There are 4 types mostly related to ISR in mulitple CPU environment.

    1. timer ISR -> it just checks the cpu's recent alive process for context switching.

                    It doesn't add new process in CPU.

                    If Cpu wants to change process, context switiching occurs based on their stacks context.

    2. internal ISR(such as page fault isr) -> just use ISR

    3. system call -> just use ISR

    4. I/O interrupt -> first, cpu is chosen by i/o apic.

    ***Key point***

    I/O apic -> select the cpu which deals with requested i/o interrupt.

    Local apic -> select the local cpu's interrupt order.

    it contains not only i.o interrupt but also internal isr.

    By its command, the isr order of each local CPU is chosen.

    But, system call is just considered as local command.

    It is just back-up in stacks, and after finishing hw interrupt, it begins again.

    ***

    if usb interrupt -> cpu 7,

    cpu 7 do roles for resolving this situation.

     a. just request for creating new process -> becomes this cpu's process

     b. request of other process managed by other CPU. -> just write its situation at kernel code

        -> After the role CPU becomes isr code (kernel mode) -> it can know interrupr occurs.

    There are 3 ways user process utlize kernel.

    1. system call -> request for returning result to their address -> kernel returns the result.

    2. IPC -> communiation between different user process

       representative way -> shared memory -> it is the good way for communicating two pre-agreed processes before.

       ex) a process -> create shared memory with key. (assign its user address to shared memory)

           b process(already known that key) -> request for connecting each other 

           -> kernel edits b's mapping table to access a's shared memory through using same real addreess value in both mapping tables.

    3. the way user processes get interrupt responses.

       Basicially, the way for checking whether the result is given is polling.(checking periodically)

       But, it uses a lot of CPU energy. So, cpu turns on the user process usually when the interrupt occurs to that process.

       Although the process which is not given the result can also be executed by CPU, but by Scheduling algorithms,

       They have low priority for executing.


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

    






    



    















    

    

    

    
