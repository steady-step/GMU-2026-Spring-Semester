## Week 6 deep dive (User process vs Kernel process)

CPU -> real mode -> virtual mode(ring0 vs ring3)

First, before entrying ring 0, kernel make mapping table of kernel.

Also, kernel remember its start point(real address) for using it on CR3 register.

Kernel virtual address range is much higher than user virtual address.

After this process, for making user's process, we need three steps.

1. Make that user process's mapping table. (it contains not only user one but also kernel one)

-> We don't need to change CR3 point when we face interrupt or system call.

2. Loading user program and set PC.

3. Change mode(Ring 0->Ring 3)

If interrupt or systemc call occurs, register's address automatically changes for starting ISR, 

and mode changes to Ring 0.

And we execute kernel code without changing CR3 register value.

Also, in same virtual memory range
