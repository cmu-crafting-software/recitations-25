# Recitation 3: Python data types manipulation

**Sam Estep** (based on 2024 recitation 3 by Matthew Davis)

_2024-01-31_

## Overview

- Previously we saw how to work with various Python types: booleans, strings, numbers, lists, dictionaries, and so on.
- Today we will get hands-on experience so that you will feel more comfortable when you work with these data types in your own projects (e.g., Wordle).

## Homework 2 Checkpoint

Who has accepted and started homework 2?

The link to accept it is in the assignment on the course website: https://cmu-crafting-software.github.io/assignments/hw2

Go ahead and accept the assignment now if you haven't already.

For today's recitation, open your repository for homework 2 in GitHub Codespaces:

- Open VS Code
- Run the command **Codespaces: Create New Codespace...**
- Type or paste the name of your homework 2 repository into the text box
- Hit <kbd>Enter</kbd> to select the repository
- Hit <kbd>Enter</kbd> again to select the `main` branch
- Use <kbd>Ctrl</kbd>+<kbd>`</kbd> to open a terminal

## In-class data manipulation exercise

Open the Python REPL: `python3`

### Booleans

- `True` -> `True`
- `False` -> `False`
- `not(True)` -> `False`
- `not(False)` -> `True`
- `b = True`
- `b` -> `True`
- `b1 = not(b)`
- `b1` -> `False`
- `b2 = not(b1)`
- `b2` -> `True`

### Strings

- `s='Hello world'`
- `s` -> `'Hello world'`
- Substrings
  - `s[4]` -> `'o'`
  - `s[-1]` -> `'d'`
  - `s[-2]` -> `'l'`
  - `s[0:4]` -> `'Hell'`
  - `s[1:4]` -> `'ell'`
  - `s[1:]` -> `'ello world'`
- Upper/lowercase
  - `s.upper()` -> `'HELLO WORLD`
  - `'YO!'.lower()` -> `'yo!'`
- Queries
  - `s.find('l')` -> `2`
  - `s.count('l')` -> `3`
- To/from lists
  - `s.split(' ')` -> `['Hello','world']`
  - `' '.join(['Hello','world'])`

### Lists

- `l=['Hello','world']`
- `l` -> `['Hello', 'world']`
- `l.append('and')`
- `l` -> `['Hello', 'world', 'and']`
- `l.extend(['good','night'])`
- `l` -> `['Hello', 'world', 'and', 'good', 'night']`
- `l.insert(1,'class')`
- `l` -> `['Hello', 'class', 'world', 'and', 'good', 'night']`
- `l.remove('world')`
- `l` -> `['Hello', 'class', 'and', 'good', 'night']`
- `l.reverse()`
- `l` -> `['night', 'good', 'and', 'class', 'Hello']`
- `l.clear()`
- `l` -> `[]`

### Dictionaries

- ` d = {'key': 'value'}`
- `d` --> `{'key': 'value'}`
- `d['key']` --> `'value'`
- Modify a key value
  - `d['key'] = 'high value'`
  - `d` --> `{'key': 'high value'}`
- Add a new key value
  - `d['students'] = 'awesome'`
  - `d` --> `{'key': 'high value', 'students': 'awesome'}`
- Get a list of keys
  - `d.keys()` --> `dict_keys(['key', 'students'])`
- Get a list of values
  - `d.values()` --> `dict_values(['high value', 'awesome'])`
- Get a list of keys with their values
  - `d.items()` --> `dict_items([('key', 'high value'), ('students', 'awesome')])`
- Loop over a dictionary's keys
  ```
  for key in d:
    print(key, 'corresponds to', d[key])
  ```
  Output:
  ```
  key corresponds to high value
  students corresponds to awesome
  ```
- Delete a key value
  - `del d['students']`
  - `d` --> `{'key': 'high value'}`
- Delete all key values
  - `d.clear()`
  - `d` --> `{}`

## Resources

- Python cheat sheet: https://perso.limsi.fr/pointal/_media/python:cours:mementopython3-english.pdf
