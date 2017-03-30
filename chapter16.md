# Chapter 16 : Programming and Operating System
The most interesting part of computer engineering is the programming! Specially when you know how it works, 
you can make better programs. Now, we designed one, and we want to program it. But wait, let's take a look at 
computers made before.

## Intel computers!
As you may remember from previous chapters, we had this for showing a simple character on console:

```assembly 
STK SEGMENT
 DW 32 DUP(?)
STK ENDS

CDS SEGMENT
 ASSUME CS:CDS, SS:STK
 MAIN PROC FAR
  MOV DL, 'A' 
  MOV AH, 02
  INT 21h
  MOV AH, 4Ch 
  INT 21h
 MAIN ENDP
CDS ENDS

END MAIN
```
And in [chapter fourteen](chapter14.md), we learned that this code will become ***Machine Code***. And now, 
we can assemble our own code, and write programs for that. 

## The assembler
Assembler is actually a software, used to generate machine code. Days we had no assembler, we had to generate machine code 
ourselves. This is hard, isn't it? But that's the only way when you have no operating system or other computer to assemble your code. 
Actually, a computer uses *Assembler* , then *Linker* to understand the programs. But in case of simple computers like ours, a simple assembler 
is enough. We just want to fill RAM blocks. The assembler sees our code. For example : 

```
AND 10, 12
``` 

and then, as we have two 8 bit inputs, it converts the 10 to `000010101` and 12 to `00001100`. And it will look at this table : 

|Ainvert|Bnegate| S2 | S1 | Instruction |
|:-----:|:-----:|:--:|:--:|:-----------:|
| 0     | 0     | 0  | 0  | AND         |
| 0     | 0     | 0  | 1  | OR          |
| 1     | 1     | 0  | 0  | NOR         |
| 1     | 1     | 0  | 1  | NAND        |
| 0     | 0     | 1  | 0  | ADD         |
| 0     | 1     | 1  | 0  | SUB         |

and finds that code for AND is `0000`. Then generates this `0x00A0C` as the final code! Let's write long numbers in hexadecimal. 
When we use hex, a 20-bit number will be a 5 digits number. So, we are the assembler in this case. Let's write our codes : 

```
AND 10, 12 
# Hex : 0x00A0C

ADD 3, 8 
# Hex : 0x20308 

SUB 10, 8
# Hex : 0x60A08
``` 

And this is a simple program in the machine language : 

```
0000 00001010 00001100
0010 00000011 00001000
0110 00001010 00001000
```
Yes, computer only understands one and zero (please re-study [chapter two](chapter2.md), if you forgot this.) and we need to generate 
a bunch of ones and zeros to make a computer work! But, computers actually need a good interface between the system and the user. What's that? 

## The operating system
Operating System, is the interface! It connects the system to the user. Operating System is a software, which lets other software be installed 
and ran on your computer. If you have a PC in home, it may run Windows or Linux as the operating system. If you have a Mac, it may run macOS. 
And if you have an iPhone, it runs iOS. There are a lot of operating systems in the world, but a few operating systems are usable. Why? because 
other ones are only made for a special purpose. For example, MINIX is made for educational purposes. If you want to learn how UNIX works, you can 
study MINIX. But operating systems such as Linux, Windows or macOS are general-purpose. They're made to be the interface.And now you may ask , 
will we write an operating system for our computer? Sorry, No! If you pay attention to our assembly code, you will find this line : 

```
MOV AH, 4Ch 
INT 21h
``` 
The part including `INT` is actually an interrupt. We have no interrupts in our computer. This is the first problem. We also have no loops in our 
computer, in instruction set, we didn't define anything to make a loop and any recursive structure. 8086 and many other *real* processors, usually 
have instructions like `branch` or `jump`, and those instructions help us make real software, including operating systems! So, we never write operating 
system for our little computer. 

## Making a real computer?
Now, you know a lot about computer architecture and organization. Also, you can make and program a computer in gate-level. This is necessary, trust me. 
You always need to know how computers work, otherwise you won't be able to make software. But I'm sure you're curious about real hardware design. The next 
chapter (and the last one!) is about that. You will learn how companies design and produce their own hardware. 