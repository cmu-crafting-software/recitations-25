# Recitation 3: Python data types manipulation, codepaces

__Matthew Davis__

_2024-02-02_

## Overview

* Previously we saw how to work with various Python types: booleans, strings, numbers, lists, dictionaries, and so on.
* Today we will get hands-on experience so that you will feel more comfortable when you work with these data types in your own projects (e.g., Wordle).
* We will also introduce GitHub Codespaces, which allows you to work on your project inside a computer owned by GitHub.
  * Why would you want to do this?
  * Getting a student GitHub account.
  * How to use Codespaces.

## In-class data manipulation exercise

Open the Python REPL: ```python3```

### Booleans
* ```True``` -> ```True```
* ```False``` -> ```False```
* ```not(True)``` -> ```False```
* ```not(False)``` -> ```True```
* ```b = True```
* ```b``` -> ```True```
* ```b1 = not(b)```
* ```b1``` -> ```False```
* ```b2 = not(b1)```
* ```b2``` -> ```True```
### Strings
* ```s='Hello world'```
* ```s``` -> ```'Hello world'```
* Substrings
  * ```s[4]``` -> ```'o'```
  * ```s[-1]``` -> ```'d'```
  * ```s[-2]``` -> ```'l'```
  * ```s[0:4]``` -> ```'Hell'```
  * ```s[1:4]``` -> ```'ell'```
  * ```s[1:]``` -> ```'ello world'```
* Upper/lowercase
  * ```s.upper()``` -> ```'HELLO WORLD```
  * ```'YO!'.lower()``` -> ```'yo!'```
* Queries
  * ```s.find('l')``` -> ```2```
  * ```s.count('l')``` -> ```3```
* To/from lists
  * ```s.split(' ')``` -> ```['Hello','world']```
  * ```' '.join(['Hello','world'])```
### Lists
* ```l=['Hello','world']```
* ```l``` -> ```['Hello', 'world']```
* ```l.append('and')```
* ```l``` -> ```['Hello', 'world', 'and']```
* ```l.extend(['good','night'])```
* ```l``` -> ```['Hello', 'world', 'and', 'good', 'night']```
* ```l.insert(1,'class')```
* ```l``` -> ```['Hello', 'class', 'world', 'and', 'good', 'night']```
* ```l.remove('world')```
* ```l``` -> ```['Hello', 'class', 'and', 'good', 'night']```
* ```l.reverse()```
* ```l``` -> ```['night', 'good', 'and', 'class', 'Hello']```
* ```l.clear()```
* ```l``` -> ```[]```
### Dictionaries
* ``` d = {'key': 'value'}```
* ```d``` --> ```{'key': 'value'}```
* ```d['key']``` --> ```'value'```
* Modify a key value
  * ```d['key'] = 'high value'```
  * ```d``` --> ```{'key': 'high value'}```
* Add a new key value
  * ```d['students'] = 'awesome'```
  * ```d``` --> ```{'key': 'high value', 'students': 'awesome'}```
* Get a list of keys
  * ```d.keys()``` --> ```dict_keys(['key', 'students'])```
* Get a list of values
  * ```d.values()``` --> ```dict_values(['high value', 'awesome'])```
* Get a list of keys with their values
  * ```d.items()``` --> ```dict_items([('key', 'high value'), ('students', 'awesome')])```
* Loop over a dictionary's keys
  ```
  for key in d:
    print(key, 'corresponds to', d[key])
  ``` 
  Output:
  ```
  key corresponds to high value
  students corresponds to awesome
  ```
* Delete a key value
  * ```del d['students']```
  * ```d``` --> ```{'key': 'high value'}```
* Delete all key values
  * ```d.clear()```
  * ```d``` --> ```{}```
  

## Homework 2 Checkpoint

Who has accepted and started homework 2? 

The link to accept it is in the assignment on the course website: https://cmu-crafting-software.github.io//assignments/hw2

Go ahead and accept the assignment now if you haven't already. 

## GitHub Codespaces

Codespaces is a **development container** that includes a Linux virtual machine that you access using the Visual Studio Code. The development container can be configured specifically for the project you are working on, so you don't have to configure (or re-configure) your own local machine for each project that you need to work on. Usually the instance of Visual Studio Code run in a web browser, but there are other ways, too.

Codespaces is a commercial product, so there can be a cost involved if you are not careful. GitHub has to pay for the compute, storage, and networking somehow. But for students, it is usually free up to a limit. But you need to have a GitHub student plan, otherwise it will cost some money.

Steps to get a GitHub student plan, which includes Codespaces credits: https://docs.github.com/en/education/explore-the-benefits-of-teaching-and-learning-with-github-education/github-global-campus-for-students/apply-to-github-global-campus-as-a-student

See which GitHub plan you are on:
* Sign into: https://github.com/
* Click your profile picture
* Click Settings-->Billing and plans-->Plans and usage
* If on a GitHub student plan you will see:
  * A coupon for $4/month (this is the student benefit)
  * A GitHub Pro plan that costs $4/month
  * A Codespaces hours quota (e.g., 180 core hours per month)

If you have a student plan, you can follow the demo below in your own hw2 repo.

### Codespaces demo

* Navigate to the hw2 repo GitHub Classroom created for you (e.g., mine is: https://github.com/cmu-crafting-software/crafting-software-hw-cmumatt)
* Click Code-->Codespaces
* Visual Studio Code opens in the browser
* You'll see the repo contents in the Explorer on the left
* Click around and open some files.
* In terminal, type: `git status`
* Change a file and save it.
* In terminal, type: `git status`
  * `git add` the file
  * `git commit -m "demo commit"`
  * `git push`
* Check the GitHub website to see that your change was pushed successfully (you might need to reload the page)
* In the terminal:
  * Type `python3` to start the Python REPL
  * Enter some Python code. For example:
    * ```l=['Hello','world']```
    * ```l``` -> ```['Hello', 'world']```
* Stop the Codespace (so it's not running, which uses your quota billable)
  * Note: GitHub will stop your Codespace automatically, but this process takes some time. During this time, the Codespace is consuming your quota. So, it's better to stop it yourself manually if you can remember to do that. 
  * Click Hamburger-->File-->Codespaces
  * Click your repo on the left side
  * On the Codespace, click `...`-->Stop Codespace


## Resources
* What is a dev container (e.g., Codespaces): https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers
* Python cheat sheet: http://sixthresearcher.com/wp-content/uploads/2016/12/Python3_reference_cheat_sheet.pdf
