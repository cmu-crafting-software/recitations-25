# Recitation 1: Git and GitHub

__Matthew Davis__

_2024-01-19_

## Announcement

* Office hours poll: appt vs. set time; Slack always good

## Overview

The goal for today is to get you ready to work on [homework 1](https://github.com/cmu-crafting-software/Homework01), which is due in two weeks. 
We will also cover the items we could not cover Wednesday and make sure you are able to work with git and GitHub.

## Initial Steps

* Install Git client: https://git-scm.com/download
* Install Visual Studio Code: https://code.visualstudio.com/
* Create GitHub account: https://github.com/ & post your GitHub id to Slack
* \[TA\] Add GitHub ids to students group
* Install GitHub Credential Manager to cache credentials: https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git

## Working with Git

* Open recitation 1 repo in web browser: https://github.com/cmu-crafting-software/Recitation01
* In your terminal, go to where you want to keep the local copy of the repository
* Clone the repo, which makes a copy of it locally: `git clone https://github.com/cmu-crafting-software/Recitation01.git`
* Create a branch w/your andrew id: `git branch <andrewid>`
* Check to see which branch you are on (it's `main`): `git status`
* Switch to the branch you created: `git checkout mcd2`
* Check to see which branch you are on (it's yours): `git status`
* Edit `foodOptions.txt` (e.g., using Visual Studio Code) and add your favorite food (or delete your least-favorite food)!
* See if you have any changes to stage (you do): `git status`
* Stage the change that you made: `git add foodOptions.txt`
* See if you have any changes to commit (you do): `git status`
* Commit the change to the local repo: `git commit -m "<brief description of the change>"`
* Push your new branch and commit to GitHub: `git push` (if you get a warning suggesting a change to your command, use that. E.g., `git push --set-upstream origin <andrewid>`)
* Check GitHub to see that your branch is now there: https://github.com/cmu-crafting-software/Recitation01 (click `Branches`)

To merge your branch into `main`:
* Switch to the `main` branch: `git checkout main`
* Merge your branch into `main`: `git merge <andrewid>` 
* Push the merge commit to GitHub: `git push`
> **Note:** Doing the above may require resolving some merge conflicts. If you are new to resolving merge conflicts, it's a good idea to check the repo afterwards to make sure you resolved them the way you intended.

## GitHub features we didn't have time to discuss Wednesday

* Pull Requests (PRs -- provides a set of basic workflows for merging branches into `main`
  * Create, Draft
  * Linking to issues
  * Merge
* Issues -- used for logging and tracking bug reports or needed features
  * Creating
  * Linking to a PR
  * Closing
* Other features: projects, wikis, CI, etc.

## Git resources
* Git cheat sheet: https://education.github.com/git-cheat-sheet-education.pdf, 
https://www.git-tower.com/blog/git-cheat-sheet/
* Branching: https://learngitbranching.js.org/
* Citing software and files: https://www.software.ac.uk/how-cite-software, https://github.com/swcarpentry/website/blob/gh-pages/CITATION
* Choosing a license: We often use an MIT License, but there are many choices. See https://choosealicense.com/ for a guide that explains some of the many choices.
