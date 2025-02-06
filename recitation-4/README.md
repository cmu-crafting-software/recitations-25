# Recitation 4: classes, objects, and sets

**Sam Estep** (based on 2024 recitation 4 by Matthew Davis)

_2025-02-07_

## Overview

In this recitation, we'll continue with our Wordle example. This time, we will:

- Provide a list of valid letters to the player.
- Build an automated player that plays the game 100 times.

## Concepts

- Sets
  - Unique members
  - Unordered
  - Set operations: union, difference, etc.
- Objects and classes
  - Examples:
    - https://docs.python.org/3/library/csv.html#csv.writer
    - https://docs.python-requests.org/en/latest/
  - Methods (aka "functions")
  - State (aka "fields")

```python
class Writer:
   row_count = 0  # field
   file = ""      # field
   # constructor
   def __init__(self, file):
     self.file = file
   # method
   def write_row(self, data):
     self.row_count += 1
     print("Wrote: ",data," to ",self.file)
writer1 = Writer("egg.csv")
writer1.write_row(["egg", "price", "color"])
writer2 = Writer("chicken.csv")
```

## Task 1: help the human players out

- Open this recitation's repo in a new Codespace: https://github.com/cmu-crafting-software/recitation04
- `git status` to see that you have checked out branch `main`
- Create and checkout your own branch: `git switch -c "[andrewid]"`
- Use `uv run pytest` to check that everything's OK so far
- Open `wordle.py` and find method/function `play()`
- `play()` is the interactive mode of the game and has an optional argument that tells it to print out valid characters after each step (`char_hint`).
- Play the game once to see this working; in your terminal:
  - `cd recitation-4`
  - `python3 wordle.py`
  - Notice the list of valid letters remaining is empty!
- In `recitation-4/wordle.py` add code to `valid_letters` to make it work.

In the desktop version of Wordle, the game shows you the characters on a colored keyboard, which is helpful for keeping track of the valid characters to use. Let's try to do that.

## Task 2: play the wordle game programmatically

The `WordleGame` **class** inside `wordle.py` represents a single game of Wordle. Let's try using it first:

- Instantiate a `WordleGame` **object** with a predefined answer `apple`.
  ```
  $ python3
  >>> import wordle
  >>> game = wordle.WordleGame('./words.json','apple')
  ```
- Guess 3 times, in which the final guess is `apple`.
  ```
  >>> game.guess('snarl')
  ['🟥', '🟥', '🟨', '🟥', '🟨']
  >>> game.guess('apply')
  ['🟩', '🟩', '🟩', '🟩', '🟥']
  >>> game.guess('apple')
  ['🟩', '🟩', '🟩', '🟩', '🟩']
  ```
- Print out the history of hints, and if you indeed won the game using methods defined in the class.
  ```
  >>> if(game.game_won):
  ...   print("YAY! You won!")
  ...   game.show_history()
  ...
  🟥 🟥 🟨 🟥 🟨
  🟩 🟩 🟩 🟩 🟥
  🟩 🟩 🟩 🟩 🟩
  ```

## Task 3: play the wordle game programmatically, many times

If you can play the game once with a program, you can play it many times.

- In `play_wordle_games`, create a loop that goes through `n` times
- In each loop iteration:
  - Instantiate a `WordleGame` **object** without a predefined answer
  - Take 5 guesses
  - Print out the history
  - Record if we won
- Finally, compute and print the success rate of your first aRTiFicIAl iNTelLigeNCe.
