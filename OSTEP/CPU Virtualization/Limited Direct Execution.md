# Limited Direct Execution
For performance reasons, we want our program to be directly run on the CPU. But for security reasons, we want the OS to intervene. So this is achieved through **Limited Direct Execution**.

## Restricted Operations
What if a process wants to perform a privileged operation, like disk I/O, that could compromise the system? We can't let user programs have direct control over devices.

The processor supports two modes:
- **User Mode**: In this mode, applications are ran. This doesn't support privileged operations.
- **Kernel Mode**: In this mode, the program has the full access to the hardware.

## System Calls
When a program needs to perform privileged operations, it runs a **trap instruction**. This is protected control transfer. 

The hardware saves all the current program states into the stack, switches the process mode to kernel mode and jumps to a pre-defined location in the OS. The predefined location is called the **trap handler**. 

The **trap handler** identifies the system call by the system call number and executes the requrired operation.

The OS sets up a **trap table** at boot time to tell the hardware the locations of all its handlers (for system calls, interrupts, etc.). 

When the OS is finished, it executes a return-from-trap instruction, which switches the processor back to **user mode** and returns control to the calling program.


## Switching between processes
If a program is directly running on the CPU, then how does the OS regain the control. The first approach is through system calls but a program may not issue system call at all.

### Hardware Timer
The approach is to use **hardware timer**. The timer runs in a interval of certain period which causes a interrupt. Thus the OS will be able to regain the control. 


## The Context Switching
When switching between two programs, the OS has to save all its state which include registers onto the hardware. When an trap instruction is executed, the state of currently running process is saved and the processor switches to the next process. In this operationi, the **Program Counter** or **Instruction Pointer** is changed. Once it's turn for the saved program to be run, the OS fetches all the saved state and put it back where it belonged.
