# Chapter 14 : Program Structure 

In previous chapter, we built the most important part of our microcontroller. In this chapter, we will take a look 
on the theory side of ***programs*** and we will define how our computer will understand programs. This is important indeed, 
because we need to write a simple *assembler* for our computer which can generate *machine code* for us. 

## Programming for a typical computer 
You have a typical computer, which is compatible with `Intel x86 Family`. At least more than %90 of computers around me are like that. 
So, I can write this piece of art and run it on my own computer, yours, my friend's, etc. 

```c++ 
#include <iostream>

using namespace std;

int main(){
    cout << "Piece of Art!\n";
    return 0;
}
``` 

But wait! If I install a C/C++ compiler on my mobile phone, tablet or gaming console, it will work! Why? The answer is easy. 
We write *programs* for all devices, everyone can use our program. In case of lower level languages like C or C++, we need to install 
the compiler on the target device, but actually we can use compiler's options to compile our code for different machines. But, in case 
of higher level languages, like Python, we only need the interpreter on the target device, and it will work! 