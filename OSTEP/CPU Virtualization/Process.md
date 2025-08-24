# Process
A process is the primary abstraction of a running program provided by the Operating System (OS). It allows the OS to manage and run multiple programs concurrently, creating the illusion of many CPUs on a system with only a few physical CPUs. This illusion is achieved through **CPU virtualization**.

## CPU Virtualization
The OS uses **time sharing** (and space sharing for resources like disk). It runs one process for a short time, then stops it and runs another. **Mechanisms** are the low-level methods to implement functionality (e.g., a context switch to stop one process and start another). **Policies** are algorithms for making decisions (e.g., a scheduling policy that decides which process to run next).

## Components of a Process
A Process composes of various components

- **Memory**: The portion of memory the process can access
- **Registers**:  **Program Counter (PC) / Instruction Pointer (IP):** Stores the address of the next instruction to be executed. **Stack Pointer:** Manages the function call stack (local variables, parameters, return addresses).
- **I/O Status**: A list of the files the process currently has open.

## Process API
It is a set of tools provided by the OS to manage the process.

- **Create**: It creates a new process.
- **Destroy**: It terminates the process.
- **Wait**: It waits for a certain process to be executed completely.
- **Miscellaneous**: It provides control for suspending, resuming a process.
- **Status**: It allows to get the information about the process.

## Process States
A process can be in a certain state.

- **Ready**: The process is ready to run.
- **Running**: The process is currently running.
- **Blocked**: The process is waiting for an I/O operation.

## OS Data Structure for Process Management
The OS has to keep track of the process that are created on the OS. This is usually stored in the **Process List**. It contains individual entry of the processes in the OS. The individual entry of the **Task List** is known as the **Process Control Block (PCB)**. The **PCB** stores different kind of information about the process such as its state, the content of the registers, PID, etc.
