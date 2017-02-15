# Chapter 7 : The First Computer

Now, you know logic and arithmetic, two basics of computers. Of course, every device with the ability of solving logical and arithmetic 
problems, is a computer! Humans are computers, calculators are computers, and that expensive (and almost useless) iPhones are computers, too. 
In this chapter, we just make the simplest computer. We need this computer in near future, as a part of other computer. That's interesting, isn't that? 

## The Function
When we decide to design a device, we need to define its function. For example, imagine a mechanical engineer who wants to design an engine, but
he doesn't describe its function! So, no one will buy that engine, because no one knows how it works or how it's made, or what's its function! 
As a good and practical design, I considered **Addition Machine**. It's a simple calculator (or computer) we can design using a few gates. 

### Boolean Algebra!
We learned boolean algebra in [chapter four](chapter4.md) and for now, we just see it in action! For designing an *Addition Machine* , we need this simple function :

```
Sum = ~AB + ~BA 
Carry = AB 
```
Did you find the point? we just need a XOR and an AND gate! 

## The Half Adder 
Imagine this circuit, which is the implementation of the function in previous part : 

![Half Adder](figures/HalfAdder.png)

The truth table for this circuit will be :

| H.A | A   | B   |  Carry (C) | Sum (S) |
|-----|:---:|:---:|:----------:|:-------:|
|     | 0   | 0   | 0          | 0       |
|     | 0   | 1   | 0          | 1       |
|     | 1   | 0   | 0          | 1       |
|     | 1   | 1   | 1          | 0       |

It makes 0, 1 and 2 for us! It's another interesting thing we can design and implement! but, it's not complete yet! Why? It does not make 3 for us, it has 2 inputs but not 4 outputs! 
So, we still need some improvements on the circuit!

## The Full Adder 
Half adder is good, but it's not everything. Of course, it can't help us make bigger adders, so we need to connect two half adders, and make a new adder wich is called
a **full adder**. A full adder, can actually make all expected outputs for us. This is the full adder :

![Full Adder](figures/FullAdder.png)

Truth table of a full adder is like this : 

| F. A | Carry-in   | A   | B   | Carry(Cout) | Sum(S) |
|------|:--------:  |:---:|:---:|:-----------:|:------:|
|      | 0          | 0   | 0   | 0           | 0      |
|      | 0          | 0   | 1   | 0           | 1      |
|      | 0          | 1   | 0   | 0           | 1      |
|      | 0          | 1   | 1   | 1           | 0      |
|      | 1          | 0   | 0   | 0           | 1      |
|      | 1          | 0   | 1   | 1           | 0      |
|      | 1          | 1   | 0   | 1           | 0      |
|      | 1          | 1   | 1   | 1           | 1      |

Now, we have ability of making a big adder! And that big adder will be our dear *Addition Machine*.      