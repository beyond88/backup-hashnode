# Introduction of compiler and interpreter

Compiler and interpreter both are one kind of translator program. They do translate our code from high-level language to low-level or convert it to binary code. Compiler and interpreter work in two different ways. Let’s give a deep dive into the compiler and interpreter. Let’s know which languages are high-level languages now in this era. The most widely used high-level languages are Python, Java, C++, C#, Visual Basic, JavaScript, PHP, and so on.


**Compiler:**
Compilers translate our code from a higher-level language to something that the computer can understand.

As to how a compiler works, that is indeed complicated. I will attempt to briefly outline the main stages of the process, but this will be a very cursory overview.

- Lexing — break up the text of the program into “tokens”. The tokens are the “words” of the programming language, such as identifiers (keywords, variable names, function names, etc.) or operators (=, *, &, etc.).
- Parsing — convert the sequence of tokens into a parse tree, which is a data structure representing various language constructs: type declarations, variable declarations, function definitions, loops, conditionals, expressions, etc.
- Optimization — evaluate constant expressions, optimize away unused variables or unreachable code, unroll loops if possible, etc. Translate the parse tree into machine instructions (or JVM byte code).

Modern compilers are very smart, consequently, and very complicated.


![0_NFctgIUL4-DkfbX5.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669356140394/FNhhfTKWk.png align="center")


**Interpreter:**
An interpreter is a computer program used to directly execute program instructions written using one of the many high-level programming languages.

The interpreter transforms the high-level program into an intermediate language that it then executes, or it could parse the high-level source code and then performs the commands directly, which is done line by line or statement by statement.

To make a long story short; an interpreter translates the high-level language line by line, which is done only when the target program is run.



![0_Eplcipufu4bYhJVa.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669356213015/krKFR1wJ7.png align="center")

**Core pros and cons of compiler and interpreter**

- An interpreter is memory efficient. On the other hand, a compiler is not memory efficient.
- Compiler: compiled code runs faster—interpreter: interpreted code run slower.
