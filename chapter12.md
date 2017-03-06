# Chapter 12 : The Computer (Theory)

As we learned some theory and definitions in [chapter ten](chapter10.md), in this chapter we're going to continue 
our ***Theory of Design***. A computer without a strong theory behind it, is like a car without engine! This is the 
saddest truth about computer engineering! If you can't present a good documentation of you design or build, you'll fail! 
To avoid fails, we learn how to design a computer (theory phase) in this chapter!

## The Instruction Set

Every computer, has an ***Instruction Set***. The way instrucions are implemented, is called ***Instruction Set Architecture*** or 
in short, ***ISA***. We need to design one for our dear computer, of course! A computer without ISA, is really impossible! There are a few
tips we should follow in our design of ISA :

* As we want to design a RISC computer, we need to simplify every instrucion we need. For example, a NOR gate can be designed 
with an AND gate with inverted inputs, So we don't need to use both NOR and AND gates! 
* We should document every step of our design, because it's our ***Computer Organization***. And in final product, that's important to 
be mentioned! 
* The last tip is that we need to model everything we designed, later, we learn more about modeling. 