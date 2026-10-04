# SY02. Operating systems

| Track | Stage | Depends on | Needed by |
|---|---|---|---|
| Systems and performance | 4. Multivariable mathematics, statistics and systems | IN05, SY01 | IN15, SY03, SY04 |

## Why this module

Loading a 4 GB weight file through `mmap`, running several training processes that share memory, limiting a test so it cannot freeze the machine, sandboxing the code an agent wants to execute, using huge pages to cut address translation costs: all of it is the operating system. This module explains the services the whole stack runs on.

## Objectives

After this module, you can explain how the operating system manages processes, threads, memory and files, use its interfaces from C and Python, and reason about scheduling, synchronization and resource limits.

## Competences evaluated

1. Explain processes and threads, their states, and create them from C (`fork`, `exec`, `wait`, POSIX threads) and from Python.
2. Explain scheduling at a basic level (time slices, priorities, `nice`) and its effect on measurements.
3. Explain virtual memory: pages, page tables, page faults, the TLB, copy-on-write, huge pages and transparent huge pages.
4. Map files and anonymous memory with `mmap`, explain lazy loading and when memory is really allocated.
5. Use files and I/O at the system-call level (`open`, `read`, `write`, `lseek`, buffering) and explain the page cache.
6. Handle signals (delivery, handlers, safe handlers, `SIGKILL` versus `SIGTERM`) and parent-death notification.
7. Communicate between processes with pipes, shared memory and Unix sockets.
8. Synchronize with mutexes, semaphores and condition variables, and recognize and avoid deadlocks and race conditions.
9. Limit resources with `ulimit` and cgroups (memory, CPU), and explain the out-of-memory killer.

## Notions, in learning order

1. **The role of the operating system**: kernel and user mode, system calls.
2. **Processes**: creation, execution, termination, process tree, zombies and orphans.
3. **Threads**: kernel threads, POSIX threads, threads versus processes.
4. **Scheduling**: preemption, priorities, multicore scheduling, timing noise.
5. **Virtual memory**: address spaces, paging, page faults, TLB, copy-on-write, huge pages.
6. **Memory mapping**: `mmap` of files and anonymous memory, demand paging, sharing.
7. **Files and I/O**: file descriptors, system calls, buffering, page cache, direct I/O (first look).
8. **Signals**: semantics, handlers, async-signal safety, `prctl(PR_SET_PDEATHSIG)`.
9. **Inter-process communication**: pipes, shared memory, Unix sockets.
10. **Synchronization**: race conditions, mutexes, semaphores, condition variables, deadlocks.
11. **Resource control**: limits, cgroups, the out-of-memory killer, why tests must run under limits.

## Practice

- Small C programs for each mechanism: a process pool with `fork`, a producer-consumer with condition variables, two processes sharing a buffer through `mmap`, a signal handler.
- Measuring the effect of huge pages and of `mmap` versus `read` on loading a large file.
- Running a memory-hungry program under a cgroup limit and observing what happens when it exceeds it.

## Evaluation format

One session, about 2 hours 30: programming tasks on processes, `mmap`, IPC and synchronization, plus questions on virtual memory, scheduling and signals. Pass mark 100 %.

## References

- Remzi H. Arpaci-Dusseau and Andrea C. Arpaci-Dusseau, *Operating Systems: Three Easy Pieces* (free book).
- Michael Kerrisk, *The Linux Programming Interface* (book, not free), and the Linux `man` pages (free).
