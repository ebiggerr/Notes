# Overview

Java language processors combine compilation and interpretation. A Java source program ==may== be first compiled into an intermediate form called ==*bytecode*==. The bytecodes are then interpreted by a virtual machine 

A benefit of this arrangement is that ==bytecodes== compiled on one machine can be interpreted on another machine, perhaps across a network.

In order to achieve faster processing of inputs to outputs, some Java compilers, called ==*just-in-time* compilers (JIT)==, translate the bytecodes into machine language ==inmmediately before they run the intermediate program to process the input==

![[hybrid compiler.png]]

