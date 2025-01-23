# Recitation 2: REST and Web APIs

**Sam Estep** (based on 2024 recitation 1 by Matthew Davis)

_2024-01-24_

## Overview

- We previously learned how to access and programmatically manipulate data locally.
- Web API: programmatic access to remote data
- REST (Representation state transfer)
  - Architecture for designing an API
  - Stateless: each't store user data
  - HTTP (Hypertext transfer protocol)
- Why REST:
  - Less overhead of keeping track of context
  - Easier for testing
- Format:
  - respond in JSON format

## Initial steps

- Open a GitHub Codespace in [this recitation's repository](https://github.com/cmu-crafting-software/recitation02)
  - Open VS Code
  - Run the command **Codespaces: Create New Codespace...**
  - Paste `cmu-crafting-software/recitation02` into the text box
  - Hit <kbd>Enter</kbd> to select the repository
  - hit <kbd>Enter</kbd> again to select the `main` branch

## The census API

- Their homepage: <https://www.census.gov/data/developers/guidance/api-user-guide.Overview.html>
  - Without an API key, you're limited to 500 queries per day
  - If you want, you can request a key here: <https://api.census.gov/data/key_signup.html>
  - To use your API key, append `&key=` followed by your key at the end of your URL
- Ways to access REST APIs:
  - Web browser
  - Python:
    ```python
    import requests
    r = requests.get('https://api.census.gov/data/2019/pep/charagegroups?get=NAME,POP&for=state:*')
    print(r.text)
    ```
  - curl:
    ```sh
    curl 'https://api.census.gov/data/2019/pep/charagegroups?get=NAME,POP&for=state:*'
    ```
- Query example
  ```
  https://api.census.gov/data/2019/pep/charagegroups?get=NAME,POP&HISP=2&for=state:*
  \_________Server address___________/\__endpoint__/\________query string__________/
  ```
- Getting overall population for each state

  ```
  https://api.census.gov/data/2019/pep/charagegroups?get=NAME,POP&for=state:*
  ```

- Getting overall population for each county

  ```
  https://api.census.gov/data/2019/pep/charagegroups?get=NAME,POP&for=county:*
  ```

- Getting 18+ population for each county
  ```
  https://api.census.gov/data/2019/pep/charagegroups?get=NAME,POP&for=county:*&AGEGROUP=29
  ```

## Exercise

1. Total population of Allegheny County

   ```
   https://api.census.gov/data/2019/pep/charagegroups?get=NAME,POP&in=state:42&for=county:003
   ```

2. Only 65+ in Allegheny County

   ```
   https://api.census.gov/data/2019/pep/charagegroups?get=NAME,POP&in=state:42&for=county:003&AGEGROUP=26

   ```

3. Under 18 Asian population of Pennsylvania
   ```
   https://api.census.gov/data/2019/pep/charagegroups?get=NAME,POP&RACE=10&AGEGROUP=19&for=state:42
   ```

## In-class Project

- Split into groups of 2-3
- Choose a specific state and county within the United States, e.g.,
  - Los Angeles County, CA
  - Wake County, NC
  - Nassau County, NY
- Use the Census API to find population information about this county
- Create a 1 page PowerPoint slide and present your findings to the class
