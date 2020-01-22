# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to a repository to complete the task. Remember to also submit your answers to Blackboard

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Concurrency: Tasks starts and run in overlapping time periods. They dont really run at the same time, but when a task is in waiting state, the CPU is assigned to another task.
Parallelism: multiple tasks or several parts of a task run at the same time.
 
 ### Why have machines become increasingly multicore in the past decade?
 > A multicore processor can run instructions on different cores at the same time,
increasing overall speed.
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > It speeds up many processes since the CPU can do other things while waiting.
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > In my opinion it makes the programmers life harder. Ideally, a programmer would have an infinitely fast computer without memory problems. Then the programmer wouldn't have to think about concurrency.
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > Process:
- managed by OS
- A virtual address space each
- Can be interrupted by the system to allow another process to run
- Can be ran in parallel
- High memory overhead
- The time overhead for creating and context switching between processes is pretty high
>Threads:
- managed by OS
- Each thread is "contained" within some particular process
- All threads in the same process share virtual address space
- Can be interrupted by the system to allow another thread to run
- Can be ran in parallel with other threads
- The memory and time overheads associated with threads are smaller than processes, but not negligible.
>Green threads:
- User-space projections of the same concept as threads, but not managed by OS.
- Probably not truly concurrent, except in the sense that there may be multiple worker threads or processes giving them CPU time concurrently,
so probably best to consider this as interleaved or multiplexed.
>Coroutines:
- Not managed by OS.
- Exactly threads, except co-operatively multitasking, and hence not truly concurrent.
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > Thread, thread, process
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > It effectively makes any CPU-bound Python program single-threaded.
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > Use co-routines instead of threads.
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > Sets the maximum number of CPUs that can be executing simultaneously and returns the previous setting.
