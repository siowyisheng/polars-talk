# DataFrames: Polars is the new Pandas

## DataFrames

Working with spreadsheets in Python.


## Comparison

polars


why?
1. written in rust (Built to allow parallel processing due to being written from Rust, while pandas is written on top of python libraries like numpy)

2. apache arrow memory format, a more efficient memory format for data processing

3. lazy execution


pandas advantages

1. established, greatest interoperability with other packages that form part of the machine learning pipeline, but polars is catching up quickly



> There should be one-- and preferably only one --obvious way to do it.
> _PEP 20, The Zen of Python_

It evolves with python versions, and so it's important to keep up.

## Benefits

### 1. Fast

Certain operations and functions are designed to be more performant.

Eg. `.join()` vs `s += c`

### 2. Familiar

Having a common standard makes it easier for programmers to work together.

Atlhough we cna raed txet lkie tihs, i'ts nto stnadrad adn nto so plaesnat.

### 3. Short

Yes.

### 4. Intuitive names

For better readability.

Eg. `random.choice()`

### 5. Less nesting

Eg. List comprehensions

## Examples

### Show a string with variables

```python
# first instinct
def user_info(user):
    return 'Name: ' + user.name + ' Age: ' + user.age





# pythonic before 2.7
def user_info(user):
    return 'Name: %s Age: %s' % (user.name, user.age)





# pythonic in 2.7
def user_info(user):
    return 'Name: {user.name} Age: {user.age}'.format(user=user)





# pythonic in 3.6+
def user_info(user):
    return f'Name: {user.name} Age: {user.age}'




```

### Return from functions

```python
# natural
def check_equal(x, y):
    result = False
    if x == Y:
        result = True
    return result





# pythonic
def check_equal(x, y):
    return x == y




```

### Check for empty values

```python
# empty string, empty list, empty dict
if not x:





# None
if x is None:





# zero
if x == 0:




```

### Loop over items

```python
sumo_wrestlers = ['Bob', 'Rob', 'Gob']





# from other languages
index = 0
while index < len(sumo_wrestlers):
    print(sumo_wrestlers[index])
    index += 1





# pythonic
for wrestler in sumo_wrestlers:
    print(wrestler)




```

### Check number is in between two values

```python
if 12 < age and age < 60:
    leave_on_board_titanic()





# pythonic
if 12 < age < 60:
    leave_on_board_titanic()




```

### Checking membership in a collection

```python
# natural
def check_membership(item, list_data):
    for item in list_data:
        if item == target:
            return True
    return False





# pythonic
def check_membership(item, list_data):
    return item in list_data




```

### Check for substring in string

```python
s = "This be a string"
# we want to write check_substring
if check_substring(s, 'is'):
    do_something()





# from javascript
def check_substring(s, substring):
    if s.find(substring) == -1:
        return False
    else:
        return True





# pythonic
def check_substring(s, substring):
    return substring in s




```

### Create a string from a list of letters

```python
letters = ['s', 'p', 'a', 'm']





# natural
word = ''
for letter in letters:
    word += letter





# pythonic, performant
word = ''.join(letters)
```

### Use index when looping

```python
# natural
def cap_2nd_char(s):
    i = 0
    new_s = ‘’
    for c in s:
        if i == 1:
            new_s += c.upper()
        else:
            new_s += c
        i += 1
    return new_s





# pythonic
def cap_2nd_char(s):
    new_s = ‘’
    for idx, c in enumerate(s):
        if idx == 1:
            s += c.upper()
        else:
            s += c
    return s




```

### Swap two variables

```python
# natural
c = a
a = b
b = c





# pythonic
a, b = b, a




```

### Get multiple return values from a function

```python
def coordinates():
    x = 1
    y = 2
    z = 3
    return x, y, z





# natural
result = coordinates()
x = result[0]
y = result[1]





# pythonic
x, y, _ = coordinates()




```

### Do something n times

```python
# natural, hard to count
make_network_request()
make_network_request()
make_network_request()
make_network_request()
make_network_request()
make_network_request()
make_network_request()
make_network_request()
make_network_request()
make_network_request()




# pythonic
for _ in range(10):
  make_network_request()
```

### Access a dictionary and use a default value

```python
# natural
log_severity = log.Info
if 'severity' in config:
    log_severity = config['severity']





# pythonic
log_severity = config.get('severity', log.Info)




```

### Work with files

```python
# harmful
file_handle = open(path_to_file, 'r')
    for line in file_handle.readlines():
        if some_function_that_throws_exceptions(line):
            # do something
file_handle.close()





# pythonic
with open(path_to_file, 'r') as file_handle:
    for line in file_handle:
        if some_function_that_throws_exceptions(line):
            # do something




```

### Check if A is either B, C or D

```python
# natural
if pokemon == 'Pikachu' or pokemon == 'Bulbsaur' or pokemon == 'Jigglypuff':
    pokemon_is_cute = True





# pythonic
if pokemon in ('Pikachu', 'Bulbsaur', 'Jigglypuff'):
    pokemon_is_cute = True




```

### Create a length-N list of the same thing

```python
ten_nones = [None] * 10




```

### Create a list of lists

```python
ten_lists = [[] for _ in range(10)] # py3




```

### Counting instances in a list

```python
fruits = ['orange', 'banana', 'apple', 'orange', 'banana']





# manual
d = {}
for fruit in fruits:
    if fruit in d:
        d[fruit] += 1
    else:
        d[fruit] = 1





# pythonic
from collections import Counter
counter = Counter(fruits)
c.values()
# Counter({'orange': 2, 'banana': 2, 'apple': 1})
# can also use Counter(fruits).most_common(2) to get the two most common items and their counts




```

### Get a random value from a collection

```python
import random
characters = "abcdefghijklmnopqrstuvwxyz1234567890"





# from C
index = random.randint(0, len(letters)-1)
item = characters[index]





# pythonic
item = random.choice(characters)




```

### Looping through multiple sequences using zip

```python
foods = ['chicken rice', 'nasi lemak', 'carrot cake']
ratings = [3, 5, 2]





# natural
for i in range(len(foods)):
    print(foods[i], ratings[i])





# pythonic
for food, rating in zip(foods, ratings):
     print(food, rating)




```

### Create a list with items

```python
numbers = range(1, 100)





# natural
prime_numbers_squared = []
for n in numbers:
    if is_prime(n):
        prime_numbers_squared.append(n ** 2)





# pythonic
prime_numbers_squared = [
    n ** 2 
    for n in numbers
    if is_prime(n)
]





# NOT pythonic to use it when you don't need the list
[print('hello') for _ in range(10)]





# pythonic
for _ in range(10):
    print('hello')




```

### Dictionary comprehensions

```python
foods = ['chicken rice', 'nasi lemak', 'carrot cake']
ratings = [3, 5, 2]





# natural
food_guide = {}
for food, rating in zip(foods, ratings):
    if rating > 2:
        food_guide.update({food: rating})





# pythonic
food_guide = {
    food: rating
    for food, rating
    in zip(foods, ratings)
    if rating > 2
}




```

### Bonus Python 3.8: List comprehension with a long/expensive function

```python
# long, slow
[long_and_expensive_func(x) for x in values if long_and_expensive_func(x) < 10]





# pythonic
[result for x in values if (result := long_and_expensive_func(x)) < 10]




```

### Sources

[Modern Polars, Kevin Heavey](https://kevinheavey.github.io/modern-polars/)

[Polars vs. pandas: What’s the Difference?, Jodie Burchell](https://blog.jetbrains.com/pycharm/2024/07/polars-vs-pandas/)
