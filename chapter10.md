# Chapter 10 : Computer Architecture 

This chapter is only theory of computer architecture. Actually, we need to know this part before we can start design
and implementation. There are a lot of concepts we should know. In this chapter, I tried to cover the most important 
concepts. 

## Computer Architecture 

The term *architecture* usually used for everything engineers build, and it means all engineers need to know the architecture
of what they made. *Computer Architecture* is simply operations that a computer can do. Do you remember our ***Addition Machine***? 
That computer had a simple architecture, it could add two numbers, and if one of inputs was negative (according to the operator of computer, not computer itself!) 
it could help us subtract. That's nice, isn't that? So ***All instructions and operations of a computer is its architecture***. This is
the only concept you actually feel when you are a *user*. When you are *engineer* you need to know more concepts. 

## Backward Compatibility 

Backward compatibility is the most important theory in computer architecture and organization. In 70's, *Intel* made 8085 processor. 
Later, they made 8086. Let's see how they implemented Backward compatibility! Imagine a program written for 8085, 8086 must support and 
execute that. Every newer designs, should be compatible with older ones. For now, I have a laptop with *Intel Core i5* processor, and I can 
execute Windows XP on it. This is Backward compatibility. 

## Computer Organization 

You know what *computer architecture* means, but what about organization? computer organization, is a level before architecture. In architecture, we just 
analyze computers instructions, and after analyzing it, we can tell ***what instructions this computer can do.***. But, the **structure of instructions* 
is not revealed yet! When we start studying structure of instructions, we actually study computer organization. 

So, when we say *our computer can multiply*, we just talked about its architecture. But, when we say *our computer includes a multiplier, which is made up of adders* , 
we spoke about its organization. So, when we are talking about *what a computer can do* we are speaking about architecture. But, when we start talking about *how instructions are 
implemented* , we are talking about organization. 

## Complex or Reduced? This is the question

A computer is measured by number of its instructions, so, when this number is less than 100, we call the design ***Reduced Instruction Set Computer*** or in short, 
**RISC**. When we have more than 100 instructions in a computer, we call that ***Complex Instruction Set Computer*** or **CISC**. The computer we design in this book, will be 
a RISC, because RISCs are easy to study, learn, implement and understand. Also, RISCs are faster than CISCs. 


