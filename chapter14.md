# Chapter 14 : Program Structure 

In previous chapter, we built the most important part of our microcontroller. In this chapter, we will take a look 
on the theory side of ***programs*** and we will define how our computer will understand programs. This is important indeed, 
because we need to write a simple *assembler* for our computer which can generate *machine code* for us. 

## Programming for a typical computer 
You have a typical computer, which is compatible with `Intel x86 Family`. At least more than %90 of computers around me are like that. 
So, I can write this piece of art and run it on my own computer, yours, my friend's, etc. 

```c++ 
#include <iostream>

using namespace std;

int main(){
    cout << "Piece of Art!\n";
    return 0;
}
``` 

But wait! If I install a C/C++ compiler on my mobile phone, tablet or gaming console, it will work! Why? The answer is easy. 
We write *programs* for all devices, everyone can use our program. In case of lower level languages like C or C++, we need to install 
the compiler on the target device, but actually we can use compiler's options to compile our code for different machines. But, in case 
of higher level languages, like Python, we only need the interpreter on the target device, and it will work! 

But let's go deeper, deep inside the Intel x86 instruction set! Let's print the expression ***Piece of Art*** on console using assembly 
language :

```assembly

STK SEGMENT
	DW 100 DUP(?)
STK ENDS

DTS SEGMENT
	TXT DB 'Hello, World!', 10, 13, '$'
DTS ENDS

CDS SEGMENT
	ASSUME CS:CDS, SS:STK, DS:DTS
	MAIN PROC FAR
		MOV AX, SEG DTS
		MOV DS, AX
		MOV DX, OFFSET TXT
		MOV AH, 09H
		INT 21H
		MOV AH, 4CH
		INT 21H
	MAIN ENDP
CDS ENDS
END MAIN
```

This is not that hard to write and understand. Anyway, we are not going to talk about assembly programming here. So, have you seen 
the code? But It's not actually what computer sees! The computer only sees & understands a bunch of 0 and 1's. So, imagine one the 
above code lines. For example this : 

```
MOV DS, AX 
``` 

When you *assemble* the code using assembler, it will turn this line to something like this : 

```
B8 0000
```

***NOTE : THIS IS NOT THE EXACT MACHINE CODE OF THAT INSTRUCTION***

Letter `B` stands for 4 bits, also 8 stands for 4 bits. We have 8 bits *Instruction Code* and 16 bits *hidden data* in 
x86 family ***Object Code***. In this chapter, we actually decide for a simple object code for our microprocessor. 