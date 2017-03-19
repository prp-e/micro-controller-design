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
	TXT DB 'Piece of Art!', 10, 13, '$'
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

## Object Code 
Now, we need to decide about a simple *Object Code* structure for our microcontroller. As I mentioned before, we won't 
have a register file in our microcontroller and we directly read data from RAM. You may ask why, because we can keep it simple 
for future developments and studies. Let's take a look at our *Instruction Table*, but this time, Hexadecimal : 

| Instruction | Code |
|:-----------:|:----:|
| AND         | 0x0  |
| OR          | 0x1  |
| NOR         | 0xC  |
| NAND        | 0xD  |
| ADD         | 0x2  |
| SUB         | 0x6  |

Now, we need to upload our *Programs* to the microcontroller. But how? How it can detect the operands? This is a simple structure 
I suggest for that : 

| Instruction Code |  Input A   | Input B  |
|:----------------:|:----------:|:--------:|
| 4 bits           | 8 bits     | 8 bits   |

We have a simple 20-bit object code for our microcontroller. Let's see if we want to add two numbers, for example 15 and 8, 
how does it look like? It will be like this : 

| Instruction Code |  Input A   | Input B  |
|:----------------:|:----------:|:--------:|
|    0x2           |   0x0f     | 0x08     |

Now, we need to verify which bits are for which part. The most valuable bits can be for our instruction code, and others can be 
for inputs. This is what I suggest : 

| Instruction Code |  Input A   |  Input B  |
|:----------------:|:----------:|:---------:|
| Bits 16 - 19     | Bits 8 - 15| Bits 7 - 0|

So, the code `0x20f08` is the correct object code for `ADD 15, 8`. 

# The Final Step?
Now we have ALU, and we will add RAM to our ALU. Then, we program it and enjoy! The book is almost finished, and there's nothing more 
to say about the hardware side of a computer. But what about software and operating system? Be patient, we will take a look at 
software and operating systems in following chapters!