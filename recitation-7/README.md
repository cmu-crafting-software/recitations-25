# Recitation 7: testing your work automatically using GitHub Actions

**Sam Estep**

_2024-03-14_

[GitHub Actions](https://github.com/features/actions) lets you tell GitHub to run your code in the cloud (for free!) anytime you change it. So for instance, if you're working on a Python project, you can use GitHub Actions to run your tests every time you `git push`. This has a few benefits:

1. It'll tell you in case you forgot (or just didn't bother) to run all your own tests before pushing. It's not _hard_ to always run your tests, but even I don't bother doing it every single time; sometimes it seems "obvious" that a change won't break anything. Sometimes I'm wrong about that, though, and then GitHub Actions catches me!
2. It gives you more confidence that your code actually runs on a computer different from your own. It doesn't tell you that your code will work _anywhere_, since the [GitHub Actions runners](https://github.com/actions/runner-images) still come with a bunch of software pre-installed, but it's still _far_ more generic than your own machine.
3. If someone wants to collaborate with you by editing your code and opening a pull request on your repo, they don't even need to know how to install the software to test your project, but GitHub will run the tests anyway! Also, on the flipside, since you've already gone through the effort to get your tests working in GitHub Actions, it's much more likely that someone else will be able to run them on their machine without too much trouble.

Let's get started!

- First, open GitHub Codespaces in the repository we'll be using for today's recitation: <https://github.com/cmu-crafting-software/recitation07>
- Make sure you're up to date with the `main` branch: `git pull`
- Then, run this command to create and switch to your own branch: `git switch -c [andrewID]`
- Go ahead and push your branch now, just so that it exists on GitHub too before we continue: `git push -u origin HEAD`

Next, we're going to create a Python project using [uv](https://docs.astral.sh/uv/) like we've done before; run these commands:

```sh
uv init
uv add pytest
```

Then create a Python test file: `recitation7_test.py`

```python
def test_numbers():
    assert 2 + 2 == 4
```

Now, we're going to create our first GitHub Actions _workflow_. Copy-paste this code into a file with this name: `.github/workflows/test.yml`

```yaml
name: Test
on: push

jobs:
  test:
    runs-on: ubuntu-24.04
    steps:
      - uses: actions/checkout@v4
      - uses: astral-sh/setup-uv@v5
      - run: uv run pytest
```

And let's test it out!

```sh
git commit
git push
```
