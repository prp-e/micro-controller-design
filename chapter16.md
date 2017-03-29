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