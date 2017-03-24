# Chapter 15 : Microcontroller 
In this chapter, we make our dear computer! You've studied previous chapters to learn how to make your very own 
computer! Actually, the most important part was *ALU*. In this chapter, we will design a simple and maybe stupid 
*Control Unit* and we add a *RAM* from logisim standard library. Then, we can program it! Let's know how we can 
do this!

## Control Unit 
This one, is a bit harder to understand. But don't worry. We're just going to make the simplest ones. We will take 
a deeper look on this unit in following chapters (and maybe books!) but for this book, we make a simple one. Let's first
define this unit. Control unit, controls programs loaded in our main memory, and controls what happens in ALU. Actually, 
control unit is made up of a device which is called *counter*. A counter is a register , or a bunch of registers which 
can count! How? the counting process is controlled by *clock pulse*. But why is it important? A counter can store 
address of a program, then its output can be input of the ***Address Bus*** of the RAM. This is the simplest use of 
a counter in a computer. 