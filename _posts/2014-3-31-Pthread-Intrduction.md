---
layout: post
title: "Pthread Intrduction"
description: "Introduction about pthread"
category:multithread
tags: [multithread]
---
{% include JB/setup %}

pthread
=======================================================================================
- - -
- - -
what is a thread
--------------------------------------------------------------------------------------
1. 线程是操作系统能够进行运算调度的最小单位。它被包含在进程中，是进程中的实际运作单位。一条线程是进程中一个单一顺序的控制流，一个进程中可以并发多个线程，每条线程执行不同的任务。

2. 同一进程中的多条线程将共享该进程中的全部系统资源，如虚拟地址空间、文件描述符和signal action等。但同一进程的多个线程各有各的调用栈（call stack）、自己的寄存器环境（register context）和自己的本地存储
<center>
<a href="http://s1370.photobucket.com/user/yalinlee/media/UNIXPROCESS_zps74e6faa3.gif.html" target="_blank"><img src="http://i1370.photobucket.com/albums/ag249/yalinlee/UNIXPROCESS_zps74e6faa3.gif" border="0" alt=" photo UNIXPROCESS_zps74e6faa3.gif"/></a>
</center>

<center>
<a href="http://s1370.photobucket.com/user/yalinlee/media/THREADWITHINUNIXPROCESS_zps534c21b8.gif.html" target="_blank"><img src="http://i1370.photobucket.com/albums/ag249/yalinlee/THREADWITHINUNIXPROCESS_zps534c21b8.gif" border="0" alt=" photo THREADWITHINUNIXPROCESS_zps534c21b8.gif"/></a>
</center>



what is pthread
---------------------------------------------------------------------------------------
1. pthread is  a standardized programming interface to realize multithread.

2. When compared to the cost of creating and managing a process, a thread can be created with much less operating system overhead. Managing threads requires fewer system resources than managing processes. 


pthread overview
----------------------------------------------------------------------------------------
1. In order for a programmer to take advantage of pthreads, it must be able to be organized into discrete, independent tasks which can execute concurrently.

2. programes having the following characteristics may be suited for pthreads:
    - work that can be executed, or data that can be operated on, by multiple tasks simultaneousl;
    - block for potentially long I/O waits;
    - use many cpu cycles in some places but not others;
    - must respond to asynchronous events;
    - some wrk is more important than other woerks(priority interrupts)

3. models for threaded programs:
    - **Manager/worker**:a single thread, the manager assigns work to other threads, the workers. tpically, the manager handles all input and parcels out works to the others task. At least two forms of the manager/worker model are common:*static work pool* and *dynamic work pool*.
    - **pipeline**: a task s broken into a series of suboperations, each of which is handled in series, but concurrently, by a different thread. an automobile assembly line best describes this model.
    - **peer**: similar to the manager/worker model, but after the main thread creats other threads, it participates in the work.

4. shared memory model
   - all threads have access to the same global, shared memory
   - threads also have their own private data
   - programmers are responsible for synchronizing access globally shared data.
   <center>
<a href="http://s1370.photobucket.com/user/yalinlee/media/SHAREDMEMORYMODEL_zpsf6a795a5.gif.html" target="_blank"><img src="http://i1370.photobucket.com/albums/ag249/yalinlee/SHAREDMEMORYMODEL_zpsf6a795a5.gif" border="0" alt=" photo SHAREDMEMORYMODEL_zpsf6a795a5.gif"/></a>
</center>

5. thread safeness
   - In a nutshell, refers an application's abilit to execute multiple threads simultaneously without "clobbering" shared data or creating "race" conditions.
   - The implication to users of external library routines is that if you aren't 100% certain the routine is thread-safe, then you take your chances with problems that could arise



