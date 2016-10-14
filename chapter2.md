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
Machines are awesome, because they only use 0 and 1 to communicate with each other. Humans are not as smart as computers in this case, because we use lots of letters in daily communications. English includes 26 letters, Persian includes 32 letters, and there are languages with more than 100 letters. Computers have only two letters, `0` and `1`. Now, let's take a look at this letters!
### Everything Binary...
OK, we told you we have two letters in machine language. So, we need to convert usual letters and numbers to words that computer can understand. We use **base 2** as a key to machine language. In base 10, the regular format of daily mathematics, we have digits 0 to 9, but in base 2, we have only 0 and 1. Every digit here is called a *binary digit* , or in short, a **bit**. But a single bit alone is not enough for us. 
### Word size
Imagine the word `hello` in English language. It has 4 characters. Also, imagine the number `42`, it has 2 digits. In computers, we need a fixed size, and our words can't we bigger or smaller than that. We call this fixed space **word size**. We need word size to compute carry digit, overflow and underflow, etc. One of the most popular word sizes, is a **byte**, which is made up of 8 bits. A simple byte is mapped like this :

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
