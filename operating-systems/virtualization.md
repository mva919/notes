
## Abstraction: Process
A process is a program that has been move from disk into memory and prepared for execution.
A process is a running program. A process can be described by its states: address space,
registers, file I/O information. We can switch between processes using a context switch 
which saves the state of the process to memeory before switching a differnt process. 

The OS provides a process API to work with processes.
Create - Create new process.
Destroy - Destroy a process.
Wait - Wait for a process to terminate.
Miscallanious Control
Status

Operating systems contain data structures to keep track of both the state of all processes.
This process list is refer to a PCB (Process Control Block) and it contains the list of
process state data structures which contain information about the address space, registers, files open, etc.

### Problem
How can we run multiple applications at the same time in a computer?

### Answer
By virtualizing the CPU

### Virtualizing the CPU
Operating systems abstract the CPU by giving applications the illusion of having
the entire CPU all for their own when in reality they are time sharing the CPU 
(assuming the CPU only has one core). Virtualizin

### What is virtualization?
The processes of creating the illusion of having one thing all for you when in 
reality it is being shared. 

# How is a program turned into a process?
When we run an executable or double click on an application icon, the OS starts by retrieving
the static set of instruction that are saved on disk usually in the form of a executable file
and loaded into memory. The OS also allocates more memory for the stack, heap, static data, etc
of the process that will be running. It then sents the process state to READY, and the process
will sit in the process list and wait to be scheduled.

# What are the different process states
READY - Process is ready to be scheduled.
RUNNING - Process is executing instructions.
BLOCKED - Process is waiting on something to finish in order to continue execution (e.g. I/O request).
ZOMBIE - In UNIX, zombie state refers to a process that exited (finished executing), and needs
its resources to be cleaned up. Since in UNIX the standard for a successfully terminated process is 
0 and any other value otherwise, the parent (or OS) can check whether the process terminated successfully
by checking the return value using the `wait()` function. 

Time sharing - When multiple thing one thing by alternating when they are using said thing,
one uses for a bit of time then the other uses for a bit of time and so on.
For example, processes time share the CPU since they alternate in executing on the CPU.

Space sharing - When multiple things share the space of something. Best example of this
is memory, multiple processes share memory and disk space. 


