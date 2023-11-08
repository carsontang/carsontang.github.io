---
layout: post
title: Computer Architecture
excerpt: Notes from reading
category: computer-architecture
tags: [computer-architecture]
mathjax: true
---

* decimal term: kilobyte, KB, $10^3$ bytes
* binary term: kibibyte, KiB, $2^{10}$ bytes
* **instruction set architecture** – abstract interface between hardware and lowest-level software that contains all information necessary to write a machine language program to tell computer what to do. Basically, the order of the 1's and 0's that make the computer do something
* **transistor** – on/off switch controlled by electricity
* **integrated circuit** – combines dozens to billions of transistors into a single chip
* **manufacturing yield** – a silicon wafer yields many chips. Some are perfect and some are flawed. Only the perfect ones can be used. Because not all the chips will be perfect, we measure the yield of a wafer. The higher the yield, the more perfect chips there are.
* branch prediction – CPU predicts what the next instruction will be and executes it. In the worst case, it's wrong and no cycles are wasted.
* Apple M1 uses ARM instruction set, which is RISC, or reduced instruction set computer. This is more power efficient since it requires fewer cycles per instruction. When each second runs 1 billion cycles, that adds up
* **system on a chip (SoC)** – put CPU, GPU, DRAM, and other circuits all very close together on one silicon die instead of having parts scattered throughout motherboard. Apple M1 is a SoC, and it uses relatively low power compared to Intel's chip, which is just a CPU.