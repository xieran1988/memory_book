
What Every Programmer Should Know About Memory
----

Ulrich Drepper Red Hat, Inc. drepper@redhat.com

November 21, 2007

## 摘要

在 CPU 的核越来越多，并且越来越快的时候，制约大部分程序的因素是内存访问。
硬件的设计者提出了很内存访问的加速方法，比如说 Cache，但程序员不注意运用
它们的话，也不会达到最优的效果。很遗憾，大多数程序猿都不清楚内存子系统的结构
和 Cache 的开销。这篇文章介绍了现代硬件的内存子系统结构，介绍了为什么
要发明 Cache，它们是怎么工作的，为什么程序猿应该更好的利用它们来使
程序达到最优效果。

## 1 Introduction

在早期，计算机的构造很简单。CPU、内存、硬盘、网卡，被整合在一起，并且它们的性能很接近。比如说，内存和网卡处理数据的速度并不比 CPU 快多少。
