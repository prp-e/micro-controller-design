# Chapter 2 : How to talk to computer?
In previous chapter, we talked about how a computer can understand us. In this chapter, we learn how to communicate with our computer, and how to command it. Let's take a look at a common *programming language*, for example, C++. 
When we want to print `Hello, World!` on C++, we write some code like this:
```c
#include <iostream.h>
using namespace std;

int main(){
 cout<<"Hello, World!\n";
 return 0;
}
```
This is called a program, and when we *compile* it, it turns to a file, usually named `a.out`. And let's run our program:
```bash
~:$ ./a.out
Hello, World!
~:$
```
And now, we've communicated with our computer, but in language which is close to ours. This kind of programming languages are called **High Level** languages. They're close to human language, and they're easy to learn. There are a lot of high level languages such as `C++`, `Python`, `Ruby`, `Go`, etc. We use them when we need. For example, for coding a school project you may use C, or Go. For coding a commercial project, you may use Python, as it's easy to learn and also have a lot of libraries. But, what if you want to code directly to your hardware?! Now, we need a language which is close to machine's language. 
## The machine code
Machines are awesome, because they only use 0 and 1 to communicate with 
each other. Humans are not as smart as computers in this case, because 
we use lots of letters in daily communications. English includes 26 
letters, Persian includes 32 letters, and there are languages with more than 100 letters. Computers have only two letters, `0` and `1`. Now, let's take a look at these letters!
### Everything Binary...
OK, we told you we have two letters in machine language. So, we need to convert usual letters and numbers to words that computer can understand. We use **base 2** as a key to machine language. In base 10, the regular format of daily mathematics, we have digits 0 to 9, but in base 2, we have only 0 and 1. Every digit here is called a *binary digit* , or in short, a **bit**. But a single bit alone is not enough for us. 
### Word size
Imagine the word `hello` in English language. It has 4 characters. Also, 
imagine the number `42`, it has 2 digits. In computers, we need a fixed size, and our words can't be bigger or smaller than that. We call this fixed space **word size**. We need word size to compute carry digit, overflow and underflow, etc. One of the most popular word sizes, is a **byte**, which is made up of 8 bits. A simple byte is mapped like this :

|7|6|5|4|3|2|1|0|
|---|:---:|:---:|:---:|:---:|:---:|:---:|---:|
|0|0|0|0|0|0|0|0|

Now, we initialized one byte using only zeros. But, we have two forms for a bit, zero or one. So, how can we convert a binary number to a decimal one?!
### Convertion, it's easy!
Now, let's take a look at a simple binary number for example : `1001`. This number is a 4 bit one, but we defined our word size 8 bits. We convert it to an 8 bit number, we just need to replace missing bits with zeros :

|7|6|5|4|3|2|1|0|
|---|:---:|:---:|:---:|:---:|:---:|:---:|---:|
|0|0|0|0|1|0|0|1|

And now, we know column 3 and 0 have value one, it's so easy to calculate:

```
2^3 + 2^0
```
now, we know `2^3` is equal to 8, and `2^0` is equal to one. So, the result is:

```
8 + 1 = 9
```

It's fine to convert binary numbers to decimal, but how can we convert a decimal number to binary? Now, we try to convert 135 to binary. We all know 135 is equal to `128 + 7`. Now, we can write this number like this :

```
2^7 + 2^2 + 2^1 + 2^0
```

So, we shall enter 1 in columns 7, 2, 1 and 0. Our result is just like this :

|7|6|5|4|3|2|1|0|
|---|:---:|:---:|:---:|:---:|:---:|:---:|---:|
|1|0|0|0|0|1|1|1|

And yes! 10000111 is our result. And there's a qestion, is there any other formats for communicating with computers? Yes! We can use base 16, too. base 16 is known as hexadecimal, and we have digits 0 to F in that format. It's wierd, isn't it? 
### Hexadecimal world welcomes you
Now, let's talk about digits. In base 10, we have 10 digits. In base 3, we have 3 digits, but what about 16? In base 16 we have sixteen digits. But how can we code our digits? It's so easy, we use Latin letters instead of numbers. This table, shows you a simple convertion among binary, decimal and hexadecimal :

|Binary|Decimal|Hexadecimal|
|------|:-----:|----------:|
|0000  |0      |0          |
|0001  |1      |1          |
|0010  |2      |2          |
|0011  |3      |3          |
|0100  |4      |4          |
|0101  |5      |5          |
|0110  |6      |6          |
|0111  |7      |7          |
|1000  |8      |8          |
|1001  |9      |9          |
|1010  |10     |A          |
|1011  |11     |B          |
|1100  |12     |C          |
|1101  |13     |D          |
|1110  |14     |E          |
|1111  |15     |F          |

These are our digits, and we learned from this table that every 4 bit is equat to one hex digit. So, we can convert a decimal number to hexadecimal one using this table, and our knowledge of binary calculations. Let's think about 158. 158 is `128 + 30`. So, We can write this number like this :

```
2^7 + 2^4 + 2^3 + 2^2 + 2^1
``` 
And now, we can draw binary conversion table for this number like this :

|7|6|5|4|3|2|1|0|
|---|:---:|:---:|:---:|:---:|:---:|:---:|---:|
| 1  | 0    |0     |1     |1     |1     |1     |0    |

Oh, 10011110, is our result. let's convert it hexadecimal! It has 8 bits, it means it has 2 digits in hexadecimal format. So, we draw a hexadecimal conversion table for this number :

| 1 | 0 |
|--------|--------:|
|1001    |1110     |

According to table, `100` is equal to 9, and `1110` is equal to E. So, our result is `9E`. 
In this sections, we learned about how computer sees data. A computer reads data in binary format, but we simplify it by showing binary numbers in hexadecimal, and of course we translate hexadecimal instructions for computer later. 

## Mathematics?
We learned how to communicate with a computer, and now, we need to know how to do arithmetic operations using a computer. In next chapter, we just take a look at how a computer can do arithmetic operations. 
