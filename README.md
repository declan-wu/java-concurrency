# java-concurrency

## Motivation, Why we use concurrency
- Responsiveness
  - responsiveness can be achieved by using multiple threads, separate thread for each task
  - achieved by multi=tasking between threads
  - concurrency = multitasking

- Performance 
  - we can create an illusion of multiple tasks executing in parallel using just a single core
  - with multiple cores we can truly tun taks completely in parallel
  - complete a complex taks much faster 
  - for large scale service
    - fewer machines
    - less money spent on hardware

#### What threads are and where they live?
When we turn on our computer, a special program called OS is loaded from the disk to memory. OS then takes over and provides an abstraction for us, and helps to interact with the hardware and CPU.  All of our applicaitons, such as text editor, web browser reside on a disk in the form of a file just like any other music files. When the user runs an application, the OS takes the program from the disk and create an instance of that program in the memory. That instance is called a **process** or sometimes called context of an application. Each process is completely isolated from any other process that runs on the system. 

Each process contains metadata like PID, the files the process open for reading and writing, the Heap that contains all the information that our app needs, the code, and at least one thread called main thread which contains a call stack and instruction pointer. Stack is a region in memory, where local variables are stored, and passed into functions. Instruction pointer points to the address of the next instruction to execute. 

### Context switch
- context switch is not cheap, and is the price of multitasking(concurrency). The act of stop one process, scheduling another process in, and stat that process. 
- each thread consumes resources in the CPU and memory 
- conext switch involves storing data for one thread, and restoring data for another thread.
- too many threads causes thrashing, which means the os is spending more time in management than real productive work. 
- threads consume less resources than processes. Context switching between threads from the same process is cheaper. Coz they share many of the same metadata 

### Thread scheduling
Problem: long thread can cause starvation; and may cause UI threads being unresponsive which leads to bad UI

dynamic priority = static priority + bonus 

### Threads vs Processes
- when to prefer multithreased architecture:
  - if task share a lot of data
  - threads are much faster to create and destroy
  - switching between threads of the same process is faster 
- when to prefer multi-process architecture
  - secrutiy and stability are of higher importance 
  - tasks are unrelated to each other. 


