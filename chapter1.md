# Chapter 1 : What's a micro controller? 
A microcontroller is a small computer, and usually *System on the Chip* (SoC), which include a processor core, memory unit and programmable input/output unit. The most famous family of microcontrollers is **AVR** or **Advanced Virtual RISC** family. This family of microcontrollers are used in boards such as [Arduino](http://arduino.cc), and they're used for industrial and educational purposes. A microcontroller, can control a toy car, and it also can control a US army drone. And this depends on microcontroller type, and the program we write for it. 
## What does a micro controller consist of? 
In this section, I only explain process core, and in other chapters, we'll study other parts such as memory unit and I/O system. 
The process core is usually made up of :

1. **Arithmetic and Logical Unit**, also known as ALU. This unit, does every logical and Arithmetic operation, and it's the most important part of a microcontroller. 

2. **Data Bus**, this part is simply a bunch of wires which transfers data between to parts of process core. 

3. **Registers** are small memory blocks, and they can store data temporarily and transfer them. We always need them, because they're our temporary memory blocks and while we run a program, we need to store inputs and outputs.
## But, How do it know?! ... 
OK, now let's talk about **How does even a computer know what we want?** . The answer is simple, for example, when we write this code for x86 family :
```assembly
MOV DX, OFFSET MSG
MOV AH, 09
INT 21H
```
and we assemble and run the code, it shows us a message (for example `Hello`). And computers can understand their owners by programs, let's go preciser. Imagine you travel Iran, and of course you can understand Iranians by speaking Persian. And Iranians can communicate with you in Persian. So, if we consider computer a foreigner, the assembly language (and in better word, machine code) is its language and we need to communicate with it in its own language. In this book, you'll find how can we generate a simple machine language, and we can do simple projects with our small computer, and enjoy!
