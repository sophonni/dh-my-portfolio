---
layout: page
title: List and its available functions
description: This notebook contain codes about storing data in a list and utilize built-in functions that comes with the list.
---

```python
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
message = "My bicycle brand is " + bicycles[0].title() + "."
print(message)
```

    My bicycle brand is Trek.


## Pop and Add Transportation


```python
friends = ['Sam', 'Miles', 'Sara', 'Stephen', 'Will', 'Sammy']
for name in friends:
    print(f"Hey " + name + "! How are you?")
```

    Hey Sam! How are you?
    Hey Miles! How are you?
    Hey Sara! How are you?
    Hey Stephen! How are you?
    Hey Will! How are you?
    Hey Sammy! How are you?



```python
transportation  = ['bike', 'car', 'truck', 'plane', 'boat']
for vehicle in transportation:
    print(f"I would like to own " + vehicle + " as my type of transportation!")
```

    I would like to own bike as my type of transportation!
    I would like to own car as my type of transportation!
    I would like to own truck as my type of transportation!
    I would like to own plane as my type of transportation!
    I would like to own boat as my type of transportation!



```python
transportation.append('motocycle')
print(transportation)
```

    ['bike', 'car', 'truck', 'plane', 'boat', 'motocycle']



```python
transportation.append('ship')
print(transportation)
```

    ['bike', 'car', 'truck', 'plane', 'boat', 'motocycle', 'ship']



```python
transportation.insert(0, 'go-kart')
print(transportation)
```

    ['go-kart', 'bike', 'car', 'truck', 'plane', 'boat', 'motocycle', 'ship']



```python
del transportation[3]
print(transportation)
```

    ['go-kart', 'bike', 'car', 'plane', 'boat', 'motocycle', 'ship']



```python
pop_ship = transportation.pop()
print(transportation)
print("Element from popped is " + pop_ship + ".")
```

    ['go-kart', 'bike', 'car', 'plane', 'boat', 'motocycle']
    Element from popped is ship.



```python
last_owned = transportation.pop()
print("The last vehicle I've owned was a " + last_owned)
```

    The last vehicle I've owned was a motocycle


## Places To Travel To


```python
place = ["Dubai", "Jamaica", "Hawaii", "Thailand", "Cambodia"]
print("Temporarily sort: ")
print(sorted(place))    #temporarily sort a list
```

    Temporarily sort: 
    ['Cambodia', 'Dubai', 'Hawaii', 'Jamaica', 'Thailand']



```python
print("Original list: ")
print(place)
```

    Original list: 
    ['Dubai', 'Jamaica', 'Hawaii', 'Thailand', 'Cambodia']



```python
place.reverse()
print(place)
```

    ['Cambodia', 'Thailand', 'Hawaii', 'Jamaica', 'Dubai']



```python
place.reverse()
print(place)
```

    ['Dubai', 'Jamaica', 'Hawaii', 'Thailand', 'Cambodia']



```python
place.sort()
print(place)
```

    ['Cambodia', 'Dubai', 'Hawaii', 'Jamaica', 'Thailand']



```python
car.sort(reverse = True)    #reverse the list in reverse alphabetical order
print(car)
```

    ['toyota', 'mercedes', 'honda', 'bmw', 'audi']


## Guest List


```python
guests = ['Micah', 'Greg', 'Tony']
for guest in guests:
    print(f"Dear {guest}, I would like to invite you to a party later tonight.")

```

    Dear Micah, I would like to invite you to a party later tonight.
    Dear Greg, I would like to invite you to a party later tonight.
    Dear Tony, I would like to invite you to a party later tonight.


## Motidified Guest List


```python
guests = ['Micah', 'Greg', 'Tony']
guests.append('Matt')
for guest in guests:
    print(f"Dear {guest}, I would like to invite you to a party later tonight.")
```

    Dear Micah, I would like to invite you to a party later tonight.
    Dear Greg, I would like to invite you to a party later tonight.
    Dear Tony, I would like to invite you to a party later tonight.
    Dear Matt, I would like to invite you to a party later tonight.



```python
while(len(guests) != 1):
    uninvited = guests.pop()
    print(f"{uninvited}, sorry but you're not welcome!")

print("\nThe only person who'll be invited to the party is " + guest[0])
```

    Matt, sorry but you're not welcome!
    Tony, sorry but you're not welcome!
    Greg, sorry but you're not welcome!
    
    The only person who'll be invited to the party is M



```python

```
