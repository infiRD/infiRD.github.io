---
layout:      post
title:       Python cheatsheet 2
description: This is a cheatsheet created during my endaevor to learn scientific python computing
date:        2017-02-19 08:16:01 +0100
categories:  python scientific
---

# {{ page.title }}

[back]({{ site.baseurl }}/)

## Operators

Normally numbers are represented similarly to BigDecimal in Java and therefore
operator / always does floating point division.

```python
3 / 2                    # = 1.5
3 // 2                   # = 1, force integer division
```

## Collections

### Lists

#### Creation, initialiasation:

```python
colors = ['red', 'blue', 'green', 'black']
colors[0]                # first element
colors[-1]               # last element
colors[5:]               # ['violet', 'pink']
colors[:2]               # ['red', 'blue']
colors[1::2]             # ['blue', 'black', 'violet']
```

Striding syntax: `colors[start:stop:stride]`

#### More operations on lists

```python
colors.sort()            # sorted by natural ordering
colors.append('white')   # append 'white' to colors list
colors.pop()             # will return and remove last
                         # appended item
rcolors = colors[::-1]   # reverse
colors.reverse()         # inplace reverse
colors + rcolors         # concatenation
len(colors)              # length
del(colors[1])           # remove element at index 1
```

### Strings

String are **immutable** lists.

```python
s1 = 'Hello, how are you?'print(s1[::-1])      # ?uoy era woh ,olleH
hello = s1[:5]                                 # Hello
you = s1[-4:-1]                                # you
(hello + ', ') * 2 + hello + ' ' + you + '!'   # 'Hello, Hello, Hello you!'
s1[::3]                                        # Hl wry?
s1.replace('l', 'z', 1)                        # Hezlo, how are you?
```

#### String interpolation

Refer to stackoverflow questions about python string interpolation
[here](http://stackoverflow.com/questions/4450592/is-there-a-python-equivalent-to-rubys-string-interpolation)
and [here](http://stackoverflow.com/questions/3542714/variable-interpolation-in-python)


```python
fruit = 'Pear'
print("Hey, {fruit}!".format(**locals()))
print("Hey, %s!" % fruit)
print("Hey, %(fruit)s!" % locals())
print("Hey, {0}!".format(fruit))

# in python 3.6+
print(f"Hey, {fruit}!")

tu = (12,45,22222,103,6)
print('{0} {2} {1} {2} {3} {2} {4} {2}'.format(*tu))
```

### Maps

In python they are called dictionaries.

```python
tel = {'emmanuelle': 5752, 'sebastian': 5578}
tel['francis'] = 5915
tel['sebastian']         # 5578
```

### Tuples

Tuples are **immutable** list.

```python
t = 12345, 54321, 'hello'
u = (0, 2)
```

### Sets

Sets are unordered collection of unique items

```python
s = set(('a', 'b', 'c', 'a'))    # {'a', 'b', 'c'}
s - set(('a', 'q'))              # {'c', 'b'}
```

### Mutable collections fun

```python
colors = ['black', 'blue', 'green', 'magenta', 'pink']
a = b = c = colors    # a = b = c = ['black', 'blue', 'green', 'magenta', 'pink']
a[0] = ''             # a = b = c = ['', 'blue', 'green', 'magenta', 'pink']
b = ['-']             # a = c = ['', 'blue', 'green', 'magenta', 'pink']
                      # b = ['-']
a[:] = [1, 2]         # a = c = colors = [1, 2] , b = ['-']
```

## Control constructs

### If-then-else

```python
if a == 1:
  print(1)
elif a == 2:
  print(2)
else:
  print('A lot')
```

### For loops

```python
for i in range(4):
  print(i)

for w in ('cool', 'powerful', 'readable'):
    print('Python is %s' % word)

for w in "Hello how are you?".split(): print(w)

for i in range(0, len(words)): print((i, words[i]))

# iterating over list with enumerate function
for index, item in enumerate(words):
   print((index, item))

# iterating over dictionary:
d = {'a': 1, 'b':1.2, 'c':1j}
for key, val in sorted(d.items()):
    print('Key: %s has value: %s' % (key, val))

# list conprehension:
list = [i**2 for i in range(4)]
[y*2 for y in ys]
```

### Conditional expressions

```python
a is b          # reference comparison
a == b          # content comparison
'pink' in c     # true if c contains 'pink'
```

## Functions

```python
def factorial(n):
    if n<=1: return 1
    else:    return n * factorial(n-1)
   - optional arguments:
def slicer(seq, start=None, stop=None, step=None):
    return seq[start:stop:step]
```

**Parameter passing:**

* in python, parameters are passed to function by value as a
  reference to object much like in Java
* if the object is mutable, it is possible to change its state inside
  a function

**global variables:**

* every f-tion has its private name space. If one needs to refer to global variable

```python
def setGlobalX(y):
    global x
    x = y
    print(x)
```

**varagrs:**

```python
def varArgs(*args, **kwargs):
print('args = ' + str(args))
print('keyword args = ' + str(kwargs))

varArgs(1, 2, 3.14, a = 'elephant', b = (1.7, 1.1))
```




