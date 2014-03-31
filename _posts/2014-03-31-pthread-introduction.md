---
layout: post
title: "pthread introduction"
description: "pthread introduction"
category: multiple thread
tags: [multiple thread]
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

