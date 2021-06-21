In addition to a ==compiler== ( [[Introduction to Compiler]] ) , several other programs may be required to create an executable target program.

![[a language processing system.png]]
A source program may be divided into modules stored in separate files. The task of collecting the source program is someties entrusted to a separate program, called a ==preprocessor==. The preprocessor may also expand shorthands, called *macros* into source language statements.

The modifed source program is then fed to a compiler. The compiler may produced an assembly language program as its output, because assembly language is easier to product as output and is easier to debug. The assembly language is then processed by a program called an ==assesmble== that produces the relocatable machine code as its output.

Large programs are often compiles in pieces, so the relocatale machine code may have to be linked togeher with other relocatae object files and library files into thecode that actually run on the machine. The ==linker== resolves external memory address, where the code in one file may refer to a location in another file. The ==loader== then puts together all of the executable object files into memory for execution.


