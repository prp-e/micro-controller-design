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

|7 |6 |5 |4 |3 |2 |1 |0 |
|---|:---:|:---:|:---:|:---:|:---:|---:|
| | | |1|1| | | |
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
