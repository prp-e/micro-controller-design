# Chapter 4 : Logical Operations
Let's talk about logic! Do you know what logic is? Logic is somekind of mathematics, mixed with philosophy in simple word. It's started by Greek philosopher, *Aristotle*. Simply, logic says : **John is taller than Ali, Ali is taller than Ahmed, so, John is taller than Ahmed**. This was a very, very simple example of a logical problem in our daily life. We can do this example for everything measurable in our daily life, souch as area, height, weight, etc.

## How many logical operations we have?
We have some simple logics, and we review all of them here, and we solve some simple problems, and create new logics.
### NOT
As we have *binary* system, we use 0 for everything **off** and 1 for everything **on**. 0 for everything **true** and 1 for everything **false**. So, here we have just one variable called **A**. Let's do NOT operation on A!

|NOT| A   | ~A |
|---|:---:|---:|
|   | 0   | 1  |
|   | 1   | 0  |

We show `NOT A` in this form :

```
~A
```

This notation, helps us write *logical functions*. Functions are operations we do on one or more variables, and it has unique answer per inputs from a bunch of variables.
### AND
This operation, is very simple, but has two logic inputs. The table of AND is like this :

|AND| A   | B   | Out |
|---|:---:|:---:|----:|
|   |0    |0    |0    |
|   |0    |1    |0    |
|   |1    |0    |0    |
|   |1    |1    |1    |

We show `A AND B` in our logical notation like this :

```
AB
```

### OR
Of course, you remember famous question from Shakespear's novel Hamlet, **To be, or not to be; this is the question!**. Now, we're going to explain what OR is. This table can explain this operation :

|OR | A   | B   |Out |
|---|:---:|:---:|---:|
|   |0    |0    |0   |
|   |0    |1    |1   |
|   |1    |0    |1   |
|   |1    |1    |1   |

One of operations needs to be **True**, and it makes whole answer true.
And, we show `A OR B` like this :
```
A + B
```
## Truth Table
You saw, we used a table, which includes inputs and outputs, and also operation. This table is called **Truth Table**.

## Let's play a game!
So, let's combine some logics and make new ones! The simplest ones are :
### NAND
It means :
```
~(AB)
```
It's `NOT(AND(A, B))` in a simple word. And we draw truth table like this :

|NAND| A   | B   | Out |
|----|:---:|:---:|----:|
|    |  0  | 0   |  1  |
|    |  0  | 1   |  1  |
|    |  1  | 0   |  1  |
|    |  1  | 1   |  0  |

### NOR
It means :
```
~(A+B)
```
It's `NOT(OR(A, B))` in a simple word. The truth table is like this :

|NOR | A   | B   | Out|
|----|:---:|:---:|---:|
|    |  0  | 0   | 1  |
|    |  0  | 1   | 0  |
|    |  1  | 0   | 0  |
|    |  1  | 1   | 0  |

Is there any more logics? of course yes! But, we will have a view on two others, in this chapter. 

## Complex Logics 
There are to other logics, which are made from other logics, I would like to call them "Complex". Because They're not as simple as NAND or NOR. 
Also, we can call them "Exclusive Logics". This is what other engineers called them. 

### Exclusive OR
This logic, is implemented like this :
```
~AB + A~B
```
So, we will have a truth table like this :

|XOR | A   | B   |Out |
|----|:---:|:---:|---:|
|    | 0   | 0   | 0  |
|    | 0   | 1   | 1  |
|    | 1   | 0   | 1  |
|    | 1   | 1   | 0  |

### Exclusive NOR 

This logic is the same as XOR, but with a little difference! If you apply a NOT function to XOR, you'll get XNOR. But, the best implementation of XNOR is this function :

```
~A~B + AB
```

And we'll get this truth table :

|XNOR | A   |  B  | Out |
|---- |:---:|:---:|---: |
|     | 0   | 0   | 1   |
|     | 0   | 1   | 0   |
|     | 1   | 0   | 0   |
|     | 1   | 1   | 1   |

## The journey to computer architecture!
Now, we know logics, and we need to learn about **Logical Circuits**, which are representation of these logics in computer science and electronics. In next chapter, we will learn how to use and design simple logical circuits, and 
then, we start designing and implementing our dear micro-controller. 