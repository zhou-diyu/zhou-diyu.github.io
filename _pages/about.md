---
permalink: /
title: "About me"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
I obtained my Ph.D. in computer science from University of California, Los Angeles ([UCLA](https://www.ucla.edu/)) advised by Prof. [Yuval Tamir](http://web.cs.ucla.edu/~tamir/). My research interests are in computer systems. Before coming to UCLA, I received my B.S. in computer science from [Peking University](https://www.pku.edu.cn/) in 2013.

Research
======
My research is in the general area of computer systems. I'm specifically interested in operating systems, virtualization, and dependable computing. My thesis is focused on building **practical, low-overhead** dependability mechanisms (fault-tolerance mechanisms and a debugging tool) for hypervisors, containers, and server applications. The approach involves identifying sweet spots in the design space of dependability mechanisms that balance soundness and overhead, leveraging hardware/operating system/hypervisor support.


Past Projects 
======
For a hypervisor, the latency to reboot a new instance to recover it from transient faults (e.g., transient bit-flips in memory or registers) is unacceptably high. [*NiLiHype*](/files/dsn18.pdf) (<ins>Ni</ins>ne <ins>Li</ins>ves <ins>Hype</ins>rvisors) is a hypervisor fault-tolerance mechanism that recovers the hypervisor from transient faults by resetting it to a quiescent state that is highly likely to be valid. Compared to the prior state-of-the-art work that is based on reboot, *NiLiHype* reduces the service interruption time during recovery from 713ms to 22ms, a factor of over 30x, while achieving nearly the same recovery success rate.


[*NiLiCon*](/files/ipdps20.pdf) (<ins>Ni</ins>ne <ins>Li</ins>ves <ins>Con</ins>tainers), to the best of our knowledge, is the first container fault-tolerance mechanism that is application- and client-transparent and supports stateful applications. *NiLiCon* adapts *Remus*, a widely used VM replication technique, to containers. A key implementation challenge is that, compared to VMs, there is much tighter coupling between the container state and the state of the underlying platform. *NiLiCon* meets this challenge with various kernel enhancements and achieves performance that is competitive with *Remus*. 

[*PUSh*](/files/micro19.pdf) (<ins>P</ins>revention of <ins>U</ins>nintended <ins>Sh</ins>aring) is a low-overhead dynamic data race detector based on requiring programmers to specify intended sharing and the use of existing memory protection hardware to detect unintended sharing. A key novelty in *PUSh* is its use of memory protection keys, a hardware feature available in some recent versions of the x86 ISA, to eliminate the overhead of multiple page tables and critically, the overhead of updating page tables every time a lock is acquired or released. *PUSh* contributes an efficient algorithm to detect incorrect annotations that can hide data races, which can be applied to other annotation-based data race detectors. Several other key performance/memory optimizations are achieved by enhancing the memory management subsystem in the kernel (this work is currently in preparation). For a set of 10 real-world benchmarks, *PUSh*’s memory overhead is less than 5.8% and performance overhead is less than 54% while detecting all the data races reported by ThreadSanitizer.






