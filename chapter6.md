# Chapter 6 : Combinational Circuits

In the previous chapter, we saw how we can make logic gates. Of course, the easy way! 
In this chapter, we're going to make circuits which are famous as *Combinational*. Because we pick some 
well-known gates, and make a circuit out of them.

## The Exclusive OR 
Do you remember XOR from [chapter four](chapter4.md)? The logical function of XOR was like this: 

```
~AB + A~B 
``` 
As you see, we need two NOT gates, two AND gates and one OR gate! Ok, let's make the circuit :

![XOR Circuit](figures/XORCircuit.png)

We also have a gate for XOR, because it's very common in circuits, and in transistor level, it's implemented much simpler. 
This is the XOR gate : 

![XOR Gate](figures/XORGate.png)

This was the simplest combinational circuit we could ever make. Let's make another one!

## The Exclusive NOR 
