---
layout: page
title: List and For Loop
description: This notebook contain codes about working with lists that contains data and how to access those data using for loops.
---

```python
pizzas = ['cheese', 'vegies', 'chicken', 'sariracha']
for pizza in pizzas:
    print(pizza)

for pizza in pizzas:
    print(f"I love {pizza} pizza!") 
print("I really like pizza with all the above topping!")
```

    cheese
    vegies
    chicken
    sariracha
    I love cheese pizza!
    I love vegies pizza!
    I love chicken pizza!
    I love sariracha pizza!
    I really like pizza with all the above topping!


## Animals


```python
animals = ['cat', 'dog', 'panda', 'penguin']
for animal in animals:
    print(animal)

print("\n")
    
for animal in animals:
    print(f"{animal.title()} would make a cute pet.")
    
print("\nAll these animals would make cute pets!")
```

    cat
    dog
    panda
    penguin
    
    
    Cat would make a cute pet.
    Dog would make a cute pet.
    Panda would make a cute pet.
    Penguin would make a cute pet.
    
    All these animals would make cute pets!


## Count to 20


```python
for num in range(1,21):
    print(num)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20



```python
for odd_numb in range(1,21,2):
    print(odd_numb)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19


## Slicing


```python
cars = ['ferrari', 'lamborghini', 'audi', 'toyota', 'mercedes']
print("First three car brands are: ")
for car in cars[0:3]:
    print("\t" + car)

print("The middle car is:")
for car in cars[2:3]:
    print("\t" + car)
    
print("The last two car brands in this list are:")
for car in cars[3:5]:
    print("\t" + car)
```

    First three car brands are: 
    	ferrari
    	lamborghini
    	audi
    The middle car is:
    	audi
    The last two car brands in this list are:
    	toyota
    	mercedes


## My Pizza, Your Pizza


```python
my_pizza = ["vegies", "pepperoni", "cheese"]
friend_pizza = my_pizza[:]

my_pizza.append("meatball")
print(my_pizza)

friend_pizza.append("sumpreme")
print(friend_pizza)

print("\nMy favorite pizzas are: ")
for my_pizza in my_pizza:
    print(my_pizza)
    
print("\nMy friend’s favorite pizzas are:")
for friend_pizza in friend_pizza:
    print(friend_pizza)
```

    ['vegies', 'pepperoni', 'cheese', 'meatball']
    ['vegies', 'pepperoni', 'cheese', 'sumpreme']
    
    My favorite pizzas are: 
    vegies
    pepperoni
    cheese
    meatball
    
    My friend’s favorite pizzas are:
    vegies
    pepperoni
    cheese
    sumpreme



```python

```
