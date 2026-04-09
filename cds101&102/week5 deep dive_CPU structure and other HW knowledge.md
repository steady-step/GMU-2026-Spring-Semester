# Week 5 deep dive

    CPU is just composed of many logic gate.

    The logic gate makes the specific command and CPU mode.

    First, in CPU, there are 3 elements. CU, alu and registers.

    First CU is composed of Sequential Circuit and Combinational Circuit.

    This element is the main component of CPU.

    We can classify bus with 3 kinds.

    First, non-shared bus (such as handshake, interrupt bus).

    In this bus, there are not any worries for overlaping one over signals.

    So, there don't need to use tri-state buffers.

    Tri state buffer is circuit which can make three condition. (0,1,Z)

    if enable=1, input : 0, output:0 , input: 1, ouput: 1

    if enable=0, input : 0, output: Z, input: 1, output:Z

    1 means connecting with VCC(+), 0 means connecting with gnd-, and Z means cutting off V.

    It can protect data and circuit through cutting off V. But, in this case, they don't need.

    Second, shared bus(printing out of register)

    In this point, tri-state buffer is essential.

    tri staet buffer can cut off V, and it can protect circuit.

    Last, shared bus(inputing point)

    In this point, tri-state buffer is not essential.

    This inputing point connects with registers. So, CU just controll the register condition with condition bit.

    CU just communicate with ALU and register with internal bus.

    First, register is just combination of flip-flop. So, each flip-flop(1bit) connects with internal bus(1bit) through input point and output point.

    And, CU controlls them through changing tri-state buffer's enable bit and register's condition bit.

    For communicating with ALU, CU uses registers also.

    For example, if we want to multiply two datas, we use R1,R2 registers.

    First, CU inserts data in R1 and moves the data to ALU through opening tri-state buffer.

    Second, Also, we use R2 registers like this and gives signal(sum) to ALU.

    ALU is just composed of combinational gate, So, after 1 clock, the calculation is done, and We also open tri-sate buffer for getting result.

    First, get a result and second, get a flag bit in next clock.

    This is just one calculation. To mulitiply, we should calculate many times for finishing one commmand.

    When using external bus, it is same. They also use handshake and tri-sate buffer, and also communicate with registers.

    But, handshake line and interrupt line don't need any tri-sate buffers like previous ones.

    

    

    
