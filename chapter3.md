# Chapter 3 : Arithmetic Operations
We do simple arithmetic operations in our daily life. For example, when you buy a candy for $2 , and you give the seller $5 banknote, he will give you $3. This is a simple subtraction we use in daily life. Or, if you want to buy a toy car for $100, and you have $80 in your pocket, you may go to bank and you will take $20 from your account. This is a simple addition and subtraction in daily life. But how a computer do that?! 

In previous chapter, we talked about how computer reads data. We talked about binary digits. In this chapter, we take a look that addition and subtraction of them. 

## Addition
How do you add two decimal numbers? for example 105 and 55. This is how we add these to numbers :

|   | 1   |    |
|---|:---:|---:|
|1  | 0   | 5  |
|   | 5   | 5  |
|1  | 6   | 0  |

We start from ones, then we add **carry** of ones to decimal. Now, we can do the same for 1100 and 0100. I know we have decided to use 8 bit word size, and so I draw 8 bits table now :

|7  |6    |5    |4    |3    |2    |1    |0  |
|---|:---:|:---:|:---:|:---:|:---:|:---:|--:|
|   |     |     |1    |1    |     |     |   |
|0|0|0|0|1|1|0|0|
|0|0|0|0|0|1|0|0|
|0|0|0|1|0|0|0|0|

Did you see, we used to empty bits for our carry. If we use a smaller word size, this carry can't be displayed in output, and that will result an error. OK, we just did a simple addition. Let's talk about a bigger one, 11000000 and 01000000. I'll draw a table for this addition :

|C  |7    |6    |5    |4    |3    |2    |1    |0   |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
|1  |1    |     |     |     |     |     |     |    |
|   |1    |1    |0    |0    |0    |0    |0    |0   |
|   |0    |1    |0    |0    |0    |0    |0    |0   |
|1  |0    |0    |0    |0    |0    |0    |0    |0   |

In column **C**, we've stored our carry. This means, we need a word size bigger than 8 bits, if we care about the final result. But, currently we don't care about it, and we just store it to a memory block called **Carry Flag** , and we'll talk about it later. Addition in binary is very, very easy. But, what about subtraction? we need a subtraction for our microcontroller, too. But how can we implement our subtraction?
## Subtraction
It's a bit difficult to do a subtraction in computers, because we have no subtraction circuit. We have *Negator* and *Adder* instead of subtractor. So, we have different ways to make a number negative. I show you three popular way, and at the end, we choose on of them as our standard. 
### Sign/Modulus System
In this system, we have a sign bit, which is equal to the most valuable bit. If it's 1, number is negative, and if it's 0, number is positive. Let's see two examples , for example we convert 36 and -66 to a S/M number :

|Decimal | S   | 6   | 5   | 4   | 3   | 2   | 1   | 0  |
|--------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
|36      |0    |0    |1    |0    |0    |1    |0    |0   |
|-66     |1    |1    |0    |0    |0    |0    |1    |0   |

Oh, let's think about this system. This system is very easy-to-use, but have two great problems :

1. It makes our word size smaller, as one of our bits wasted. 
2. It makes negative zero condition, and we need to use algorithms designed for this system. These algorithms are not popular, so we don't use S/M. 

There's another easy way, and it's called **One's complement**. 
### One's Complement System
In this system, we just invert bits. Every 0 becomes 1, and every 1 becomes 0. Let's calculate -36 in this system. 

|Decimal | 7   | 6   | 5   | 4   | 3   | 2   | 1   | 0  |
|--------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
|36      | 0   | 0   | 1   | 0   | 0   |1    | 0   | 0  |
|-36     | 1   | 1   | 0   | 1   | 1   |0    | 1   | 1  |

This system is much better than S/M. but still have a great problem. It still makes negative zero, and it's not good for us. So, we have a final solution! that's using two's complement system!

### Two's Complement System
This system is very similar to one's complement, but we just add 1 to one's complement, and it makes two's complement for us. Let's calculate -67 in this system :

|Decimal | 7   | 6   | 5   | 4   | 3   | 2   | 1   | 0  |
|--------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
|67      | 0   |1    |0    |0    |0    |0    |1    |1   |
|        | 1   |0    |1    |1    |1    |1    |0    |0   |
|        |     |     |     |     |     |     |     |1   |
|-67     | 1   |0    |1    |1    |1    |1    |0    |1   |

In this system, we have no negative zero conditions, and all bits used efficiently. Now, we choose this system as our standard, and we'll design our subtraction parts using this system.

### How to subtract?
OK, now we are able to make negative numbers. So, a subtraction operation is simply *addition of a number, to a negative number* . So, for example :

```
125 - 36
```

is actually :

```
125 + (-36)
```

So, first, we calculate -36 :

|Decimal |7    |6    |5    |4    |3    |2    |1    |0   |
|--------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
|36      |0    |0    |1    |0    |0    |1    |0    |0   |
|        |1    |1    |0    |1    |1    |0    |1    |1   |
|        |     |     |     |     |     |     |     |1   |
|-36     |1    |1    |0    |1    |1    |1    |0    |0   |

And now, we do our addition :

|C  |7    | 6   | 5   | 4   | 3   | 2   | 1   | 0  |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
|   |1    |1    |1    |1    |1    |     |     |    |
|   |0    |1    |1    |1    |1    |1    |0    |1   |
|   |1    |1    |0    |1    |1    |1    |0    |0   |
|1  |0    |1    |0    |1    |1    |0    |0    |1   |

The carry is here normal, and every subtraction shall have one, now, we can do every subtraction with this method. The carry has a role now, we call it **Sing Flag** and when we want to design our final process core, we will consider a bit for this bit, too. In next chapter, we'll learn logical operations, which are very important in every computer. 
