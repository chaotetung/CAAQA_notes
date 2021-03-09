# Foreword
- Moore's Law: the maximum number of transistors in an integrated circuit doubles approximately every two years.
- Dennard Scaling: the reduction of MOS supply voltage is in concert with the scaling of feature sizes, so that as transistors get smaller, their power density stays roughly constant.
- New technologies such as 2.5D stacking, new nonvolatile memories, and optical interconnects have been developed to provide more than Moore.
- Today single-core performance is improving very slowly.
# Preface
- The instruction set architecture is playing less of a role today than in 1990.
- Single-thread performance of general-purpose microprocessors has stalled.
# 1 Fundamentals of Quantitative Design and Analysis
## 1.1 Introduction
- The rapid improvement of computer performance come both from technology advances and design innovations.
- The RISC-based machines focused the attention of designers on two critical performance techniques, the exploitation of *instruction-level parallelism* (initially through pipelining and later through multiple instruction issue) and the use of caches (initially in simple forms and later using more sophisticated organizations and optimizations).
- Because current and voltage couldn't keep dropping and still maintain the dependability of integrated circuits, *Dennard scaling* ended around 2004. This change forced the microprocessor industry to use multiple efficient processors or cores instead of a single inefficient processor.
- Whereas the compiler and hardware conspire to exploit ILP implicitly without the programmer's attention, DLP,TLP, and RLP are explicitly parallel, requiring the reconstructuring of the application so that it can exploit explicit parallelism.
- The combination of
  - transistor no longer getting much better because of the slowing of Moore's Law and the end of Dennard scaling,
  - the unchanging power budgets for microprocessors,
  - the replacement of the single power-hungry processor with several energy-efficient processors, and
  - the limits to multiprocessing to achiveve Amdahl's Law
  
  casued improvements in processor performance to slow down, that is, to ***double every 20 years***, rather than every 1.5 years as it did between 1986 and 2003.
  ***The only path left to improve energy-performance-cost is specialization.***
- This text is about the architectural ideas and accompanying ***compiler*** improvements that made the incrdible growth rate possible over the past century, the reasons for the dramatic change, and the challenges and initial promising approaches to architectural ideas, ***compilers***, and ***interpreters*** for the 21st cenruty.
## 1.2 Classes of Computers
**Desktop Computing**
- Desktop computing can be resonably well charaterized in terms of applications and benchmarking, though the increasing use of web-centric, interactive applications poses new challenges in performance evaluation.

**Classes of Parallelism and Parallel Architectures**
- There are basically two kinds of parallelism in applications:
  1. *Data-level parallelism(DLP)* arises because there are many data items that can be operated on at the same time.
  2. *Task-level parallelism(TLP)* arises because tasks of work are created that can operate independently and largely in parallel.
- Computer hardware in turn can exploit these two kinds of application parallelism in four major ways:
  1. *Instruction-level parallelism* exploits data-level parallelism at modest levels with compiler help using ideas like pipelining and at medium levels using ideas like speculative execution.
  2. *Vector architectures, graphic processor units(GPUs), and multimedia instruction sets* exploit data-level parallelism by applying a single instruction to a collection of data in parallel.
  3. *Thread-level parallelism* exploits either data-level parallelism or task-level parallelism in a tightly coupled hardware model that allows for interaction between parallel threads.
  4. *Request-level parallelism* exploits parallelism among largely decoupled tasks specified by the programmer or the operating system.
