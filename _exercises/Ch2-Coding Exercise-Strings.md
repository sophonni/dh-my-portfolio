---
layout: page
title: Upper, Lower, Title, and print statement
description: This notebook contain codes about using built-in function such as upper, lower, title, and print statement in order to work with text.
---

## Simple Message


```python
str = "Welcom to Class"
print(str)
```

    Welcom to Class


## Simple Message


```python
str = "I like dogs."
print(str)
print("\nMeant to say: ")
str = "Hi! My name is Sophonni Dy."
print(str)
```

    I like dogs.
    
    Meant to say: 
    Hi! My name is Sophonni Dy.



```python
str = str + " I'm currently a sophmore studying CS."
print(str)
```

    Hi! My name is Sophonni Dy. I'm currently a sophmore studying CS.


## Personal Message


```python
fstr = "Tufts University"
print(f"I'm a student at {fstr}.")
```

    I'm a student at Tufts University.


## Name Case


```python
name = "sophonni"
print(name.upper())
print(name.lower())
print(name.title())
```

    SOPHONNI
    sophonni
    Sophonni


## Remove Space


```python
string = "    Professor Micah"
print(string.lstrip())    #Remove left space
```

    Professor Micah



```python
string = "Professor Micah    "
print(string.rstrip())    #Remove right space
```

    Professor Micah


## Quote in a String


```python
quote = 'Hannah Arendt once said, "This is the precept which I have lived: Prepare for the worst; expect the best; take what comes."'
print(quote)
```

    Hannah Arendt once said, "This is the precept which I have lived: Prepare for the worst; expect the best; take what comes."


## Strip Name


```python
tabbed_name = "\tSophonni Dy"
print(tabbed_name.lstrip())    #remove \t
new_line_name = "\nElon Musk"
print(new_line_name.lstrip())  #remove \n
```

    Sophonni Dy
    Elon Musk


## Adding Comment


```python
name = "David Hammer"
print(name.lower())  # prints in lower case
print(name.upper())  # prints in upper case
print(name.title())  # prints in title case
```

    david hammer
    DAVID HAMMER
    David Hammer

