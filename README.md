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

Each process contains metadata like PID, the files the process open for reading and writing, the Heap that contains all the information that our app needs, the code, and at least one thread called main thread which contains a call stack and instruction pointer. 