<h1 align="center">
    cs61a
</h1>

## lecture 4

1. how to show the result of doctest in docstring

​		`python -m doctest -v xx.py`

2. how to transfer an interact interface

   `python -i xx.py`

3. functions can be manipulated as ***values and arguments***

   > higher-order function : take another function as an argument

​		![image-20230128114736897](image/cs61a/image-20230128114736897.png)



## lecture 5

##### environment diagrams for nested def statements

- how to draw -- using python tutor

##### lambda expression

```python
>>>x = 10
10
>>>square = x * x
>>>square = lamda x:x * x # a simple function
						  # with formal parameter x 
    					  # returns the value of x * x
>>>square
<function <lambda> at 0x1003c1bf8>
>>>def square(x):
...	   return x * x
...
>>>square
<function square at 10293e730>
>>>square(4)
16
>>>square(10)
100
>>>(lambda x: x * x)(3)
9
```

#####  function currying   (Haskell Curry  rediscovered)

> a way of manipulating functions,higher-order functions

```python
def curry2(f):#2 represents two parameteres
    def g(x):
        def h(y):
            return f(x,y)
        return h
    return g
```

```python
###terminal
>>>from operator import add
>>>add(2,3)
5
>>>m=curry2(add)
>>>add_three=m(3)
>>>add_three(2)
5
>>>add_three(2010)
2013
>>>curry2=lambda f:lambda x:lambda y:f(x,y)
		  #f is a parameter
>>>m=curry2(add)
>>>m(2)(3)
5
```



## lecture 6

##### wave files

​	the use of HOF



## lecture 7

##### return

```python
def search(f):
    x=0
    while not f(x):
        x+=1
    return x

def inverse(f):
    """Return g(y) such that g(f(x))->x."""
    return lambda y:search(lambda x:f(x)==y)

def square(x):
    return x*x

>>>sqrt=inverse(square)
>>>square(16)
256
>>>sqrt(256)
16
```

##### Control statement

1. if-else

##### Control Expressions

```python
"""
<left> and <right>
<left> or <right>
not <express>
"""

# the sequence of evaluating
```

##### Function Abstraction

##### Errors & Traceback

|       | Errors                                           |
| ----- | ------------------------------------------------ |
| types | syntax,runtime(TypeError...),logical or behavior |

​	how to correct them -- test



## lecture 8

##### review

##### implementing functions

​	read the description

​					$\downarrow$

verify the examples & pick a simple one

​					$\downarrow$

​	finish the function



## lecture 9

##### recursive functions

​	base cases and recursive cases

##### recursion in Environment Diagrams

```python
def fact(n):
    if n==0:
        return 1
    else:
        return n*fact(n-1)
   

```



## lecture 10

<h5> Tree recursion
</h5>

```python
from ucb import trace

@trace  
#is called decorator,@trace before the func
#display when it's called and when it returns
def fib(n):
    if n==0:
        return 0
    elif n==1:
        return 1
    else:
        return fib(n-2)+fib(n-1)

    
python -i fib.py
>>>fib(0)
fib(0):
fib(0) -> 0
0
>>>fib(1)
fib(1) -> 1
1
>>>fib(2)
fib(2):
    fib(0):
	fib(0) -> 0
    fib(1):
    fib(1) -> 1
fib(2) -> 1
1
>>>
```



## lecture 11

##### list

