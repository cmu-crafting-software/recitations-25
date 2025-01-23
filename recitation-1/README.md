# Recitation 1: Git and GitHub

**Sam Estep** (based on 2024 recitation 1 by Matthew Davis)

_2025-01-17_

## Overview

The goal for today is to get you ready to work on [homework 1](https://github.com/cmu-crafting-software/homework01), which is due in two weeks.
We will also cover the items we could not cover Wednesday and make sure you are able to work with git and GitHub.

## Initial Steps

- Create GitHub account: https://github.com/ & post your GitHub id to Slack
- \[TA\] Add GitHub ids to students group
- Install [Visual Studio Code](https://code.visualstudio.com/)
- Install the [GitHub Codespaces extension](https://marketplace.visualstudio.com/items?itemName=GitHub.codespaces)
- Run the VS Code command **Codespaces: Create New Codespace...**
- Paste `cmu-crafting-software/recitation01` into the text box and hit <kbd>Enter</kbd> to select the repository for this recitation, then hit <kbd>Enter</kbd> again to select the `main` branch

## Working with Git

- Open the VS Code terminal in the newly opened Codespace
- Check to see which branch you are on (it's `main`): `git status`
- Create and switch to a new branch with your Andrew ID: `git switch -c [andrewID]`
- Check to see which branch you are on (it's yours): `git status`
- Edit `foodOptions.txt` using VS Code and add your favorite food (or delete your least-favorite food)!
- See if you have any changes to stage (you do): `git status`
- Stage the change that you made: `git add foodOptions.txt`
- See if you have any changes to commit (you do): `git status`
- Commit the change to the local repo: `git commit -m "<brief description of the change>"`
- Push your new branch and commit to GitHub: `git push` (if you get a warning suggesting a change to your command, use that. E.g., `git push --set-upstream origin [andrewID]`)
- Check GitHub to see that your branch is now there: https://github.com/cmu-crafting-software/recitation01 (click `Branches`)

To merge your branch into `main`:

- Switch back to the `main` branch: `git switch main`
- Merge your branch into `main`: `git merge [andrewID]`
- Push the merge commit to GitHub: `git push`
  > **Note:** Doing the above may require resolving some merge conflicts. If you are new to resolving merge conflicts, it's a good idea to check the repo afterwards to make sure you resolved them the way you intended.

## GitHub features we didn't have time to discuss Wednesday

- Pull Requests (PRs) -- provides a set of basic workflows for merging branches into `main`
  - Create, Draft
  - Linking to issues
  - Merge
- Issues -- used for logging and tracking bug reports or needed features
  - Creating
  - Linking to a PR
  - Closing
- Other features: projects, wikis, CI, etc.

## Git resources

- Git cheat sheet: https://education.github.com/git-cheat-sheet-education.pdf,
  https://www.git-tower.com/blog/git-cheat-sheet/
- Branching: https://learngitbranching.js.org/
- Citing software and files: https://www.software.ac.uk/how-cite-software, https://github.com/swcarpentry/website/blob/gh-pages/CITATION
- Choosing a license: We often use an MIT License, but there are many choices. See https://choosealicense.com/ for a guide that explains some of the many choices.
