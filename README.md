# GCC Minus

An ANSI C99 compiler that translates source code into RISC-V machine instructions.

The compiler is constructed in three phases:

1. 🪄 Scanning and parsing - A scanner and parser built on top of Flex and Bison, parse the ANSI C99 syntax.
2. 🌳 Intermediate representation - The AST is an intermediate data structure that represents the full structure of the program. It is the input to the next phase.
3. ⚙️ Code generation - The AST is traversed to emit low-level RISC-V assembly instructions. Optimizations can be applied at this stage.

Building a compiler involves implementing complex translation processes and dealing with issues such as context sensitivity and variable scoping. This project aims to gain a deep understanding of compiler design and construction by building a complete pipeline to translate C programs to run on a RISC-V machine. 

If the topic and scope of the project are reminiscent of a graduate-level CS university course, that's because it is. The project is based on the [052811 VU](https://ufind.univie.ac.at/en/course.html?lv=052811&semester=2023S) course at the University of Vienna.