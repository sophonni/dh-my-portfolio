---
layout: page
title: Variables, Strings, Numbers, and Lists
description: This notebook contain codes about variables, strings, numbers, and lists
---

# Heading 1
## Heading 2
This is plain text.
* item one
* item two
* "m" for markdown
* "shift + return" for run
* "dd" for deleting a section

[This is a link to google](https://www.google.com/)


## Variables


```python
greeting = "Hello World!"
```


```python
print(greeting)
```

    Hello World!



```python
myIntro = "Hi! My name is Sophonni Dy."
print(myIntro)
```

    Hi! My name is Sophonni Dy.



```python
myIntro = "I'm Sophonni!"
print(myIntro)
```

    I'm Sophonni!



```python
ex = "This is a string."
print(ex)
```

    This is a string.



```python
ex2 = 'This is also a string.'
print(ex2)
```

    This is also a string.



```python
ex4 = 'I asked a question, "When should I use single quotes?"'
print(ex4)
```

    I asked a question, "When should I use single quotes?"



```python
historian = "edward gibbon"
print(historian)
```

    edward gibbon



```python
print(historian.title())
```

    Edward Gibbon



```python
novelist = "Becky Chamber"
print(novelist.lower())
```

    becky chamber



```python
"becky" == "becky"
```




    True




```python
"becky" == "Becky"
```




    False




```python
firstName = "ada"
lastName = "lovelice"
fullName = firstName + " " + lastName
print(fullName.title())
```

    Ada Lovelice



```python
greeting = f"Hello, {firstName} {lastName}!"
print(greeting.title())
```

    Hello, Ada Lovelice!


## Whitespcae


```python
print("tab")
```

    tab



```python
print("\ttab")
```

    	tab



```python
print("Language: \nGreek\nLatin\nLatin")
```

    Language: 
    Greek
    Latin
    Latin



```python
str_rspace = "string      "
print(str_rspace)
```

    string      



```python
print(str_rspace.rstrip())    #rstrip() command is used to strip out space from the right of the string
```

    string



```python
example = str_rspace + "."
print(example)
```

    string      .



```python
example_2 = str_rspace.rstrip() + "."
print(example_2)
```

    string.



```python
str_rlspace = "   Sophonni   "
print(str_rlspace.strip())    #strip() command is used to strip out space from the left and the right of the string
```

    Sophonni



```python
str_lspace = "    Sophonni"
print(str_lspace.lstrip())    #lstrip() command is used to strip out space from the left of the string
```

    Sophonni



```python
sum = 500 + 100
```


```python
sum
```




    600




```python
type(sum)    #returns the type of the variable
```




    int




```python
30 / 10    #this will returns the float
```




    3.0




```python
f = 30 / 7
f
```




    4.285714285714286




```python
type(f)
```




    float




```python
3 ** 3    #3 to the power of 3
```




    27



## Lists


```python
subjects = ['classic', 'history', 'philosophy']
print(subjects)
```

    ['classic', 'history', 'philosophy']



```python
print(subject[0])
```

    classic



```python
print(subjects[-1])    #-1 means starting from the back
```

    philosophy



```python
message = f"My most difficult subject is {subject[1].title()}."    #f" " is putting is a string in an fstring
                                                                   #title() is a command to turn the first letter of the given string into upper case
print(message)
```

    My most difficult subject is History.



```python
#modify a list
subjects[1] = 'sociology'
print(subjects)
```

    ['classic', 'sociology', 'philosophy']



```python
subjects.append('Computer Science')    #adding an element to the back if the list
print(subjects)
```

    ['classic', 'sociology', 'philosophy', 'Computer Science']



```python
subjects.append('Linear Algebra')
print(subjects)
```

    ['classic', 'sociology', 'philosophy', 'Computer Science', 'Linear Algebra']



```python
#insert
subjects.insert(0, 'Calculus')    #insert means insert an element to the spcific index of the list
print(subjects)
```

    ['Calculus', 'classic', 'sociology', 'philosophy', 'Computer Science', 'Linear Algebra']



```python
subjects.insert(2, 'Physics')
print(subjects)
```

    ['Calculus', 'classic', 'Physics', 'sociology', 'philosophy', 'Computer Science', 'Linear Algebra']



```python
#delete item
del subjects[-1]
print(subjects)
```

    ['Calculus', 'classic', 'Physics', 'sociology', 'philosophy', 'Computer Science']



```python
#pop will pop item where its argument is the idex of an element to be pop from the list
pop_item = subjects.pop(3)
print(pop_item)
print(subjects)
```

    sociology
    ['Calculus', 'classic', 'Physics', 'philosophy', 'Computer Science']



```python
#remove will remove item from the list where its argument is the item itself
subjects.remove('classic')
print(subjects)
```

    ['Calculus', 'Physics', 'philosophy', 'Computer Science']



```python

```
