# ch02intro
Introduction to OS, Chapter 02

Read [Introduction to OS](http://pages.cs.wisc.edu/~remzi/OSTEP/intro.pdf) and answer the following review questions.

1. **What is an operating system? What does it do?** OS is a body of software, that is responsible for making it easy to run programs, allowing programs to share memory, enabling programs to interact with devices.
2. **What is virtualization?** virtualization-process when the OS takes physical resource and transforms it into a more general ,powerful, and easy-to-use virtual form of itself.
3. **How does an OS provide access to its features?** OS provides system calls to run programs, access memory and devices,
and other related actions, we also sometimes say that the OS provides a standard library to applications.
4. **What illusion does a virtualized CPU provide?** the illusion that the system has a very large number of virtual CPUs. Turning a single CPU into a seemingly infinite number of CPUs and thus allowing many programs to seemingly run at once is what we call virtualizing the CPU, the focus of the first major part of this book
    - **How does this affect the user experience?** they are the major way in which most users interact with operating systems.
    - **How does this affect the developer experience?** you would be nice to this operator, so that they might move your job to the front of the queue.
    - **What if the CPU were not virtualized?** if we won't virtualize CPU, we won't use any programs
5. **What is a memory address?** one must specify an address to be able to access the data stored there
6. **What is memory virtualization?** Each process accesses its own private virtual address space (sometimes just called its address space), which the OS somehow maps onto the physical memory of the machine.
    - **Why would we want this?** A memory reference within
one running program does not affect the address space of other processes (or the OS itself); as far as the running program is concerned, it has physical memory all to itself.
8. **What happens if you write a C/C++ program that writes past the end of an array?**  You’re writing into memory that has not been reserved for the use of that array, so nothing may happen, or else you may overwrite some bit of memory something else in your program was using, causing it to crash
      - **Can this affect other programs?** Your operating system will almost certainly protect it from messing up any other program. It can only access its own memory space.
9. **What is a thread?** a thread of execution is the smallest sequence of programmed instructions that can be managed independently by a scheduler
10. **Why would we ever write a multi-threaded program?** it should be faster
11. **What is atomicity?** possibility of executing instructions at the same moment of time
    - **Is a C/C++ statement atomic?** No, the C standard doesn't guarantee atomicity, and in practice, the operation won't be atomic
    - **Is a Java statement atomic?** yes, most of operations are atomic
    - **Is an assembler statement atomic?** yes

13. **What does persistence mean?** persistence refers to the characteristic of state that outlives the process that created it.

14. **How does OS hard drive virtualization differ from CPU & memory virtualization?** Each virtual machine appears to run on its own CPU (or a set of CPUs), fully isolated from other virtual machines. Registers, the translation lookaside buffer, and other control structures are maintained separately for each virtual machine.
A contiguous memory space is visible to each virtual machine. However, the allocated physical memory might not be contiguous. Instead, noncontiguous physical pages are remapped and presented to each virtual machine. With unusually memory-intensive loads, server memory becomes overcommitted. In that case, some of the physical memory of a virtual machine might be mapped to shared pages or to pages that are unmapped or swapped out.
Virtual machine uses a virtual hard disk to store its operating system, program files, and other data associated with its activities. A virtual disk is a large physical file, or a set of files, that can be copied, moved, archived, and backed up as easily as any other file. You can configure virtual machines with multiple virtual disks.

15. **How does running multiple programs at the same time increase CPU efficiency?**  the OS would load a number of jobs into memory and switch rapidly between them, thus improving CPU utilization. This switching was particularly important because I/O devices were slow; having program wait on the CPU while its I/O was being serviced was a waste of
CPU time.
16. **What is multiprogramming?** Multiprogramming is a rudimentary form of parallel processing in which several programs are run at the same time on a uniprocessor
