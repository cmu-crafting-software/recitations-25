# Recitation 7: Deploying your visualization to the internet using GitHub Pages

__Matthew Davis__ (based on Wode "Nimo" Ni's 2022 recitation 7)

_2024-03-29_

## Setup Github Pages

GitHub Pages is a deployment service that lets you automatically deploy your website. Today we will be deploying one of your visualizations from HW6 onto the web for the whole world to see.

* Accept the `student-site` assignment: <https://classroom.github.com/a/-PmHW5eA>.
* Go to `student-site-<githubid>` on GitHub and setup GitHub Pages.
  * Settings -> Pages
  * Choose `main` under "Branch."
  * Hit "Save."
* Clone the repo, `student-site-<githubid>`, locally or open it in Codespaces
  * Push an empty commit: `git commit --allow-empty -m "trigger pages"` then `git push`
  * After a few minutes, your page should be up!
  * Find the URL for your page here on GitHub: Repo `student-site-<githubid>` -> Settings -> Pages -> Visit Site
  * Reference: <https://docs.github.com/en/pages/quickstart>
* Paste your GitHub pages URL (the one with the default visualization) into the `#spring-24-crafting-software` Slack channel.

## Refresh on HTML and CSS

* HTML (HyperText Markup Language) is the standard markup language for Web pages. It defines the **content** of the webpage.
  * Note: Markdown (what you write in, e.g., `README.md`) is converted to HTML
  * `<div>`: used as a container for HTML elements -- which is then styled with CSS or manipulated with JavaScript
  * Helpful HTML cheat sheets: 
    * <https://github.com/iLoveCodingOrg/html-cheatsheet/raw/master/html-cheatsheet.pdf>
    * <https://developer.mozilla.org/en-US/docs/Learn/HTML/Cheatsheet>
* CSS (Cascading Style Sheet): defines the **styling** of HTML components (e.g. color, margin, layout etc.)
  * Selectors: classes, ids, tag types
  * Inline styling
  * The DOM inspector in F12 Developer Tools
  * Helpful CSS cheat sheet: <https://github.com/iLoveCodingOrg/css-cheatsheet/raw/master/css-cheatsheet.pdf>
* JavaScript: everything else that's fancy: interactivity and animations
* More on CSS and JS later! 

## Deploy your favorite visualization to the internet

* Export your favorite Altair visualization from HW6:
  * **Hint**: We did this in lecture this week using, e.g., `chart.save("index.html")`
  * Reference: https://altair-viz.github.io/user_guide/saving_charts.html#html-format
  * You will end up with a `.html` file that contains your visualization
* Overwrite the visualization in the starter repository (`index.html`) with the one you just exported  
  * Add a title `<title></title>`, heading `<h1></h1>`, and paragraph `<p></p>` that describe your visualization
  * Add a bulleted list `<ul><li>item 1</li><li>item 2</li></ul>` with some interesting facts.
  * To update your new website on the internet: add, commit, and push to your remote GitHub repo
  * GitHub Pages will build and deploy the changes you pushed to your website automatically after a few minutes
* Explore some of the other CSS and HTML options
  * Remmeber to add, commit, and push to your remote GitHub repo frequently!
* Take a look at some of the pages in the Slack channel. Do you see anything you like? Try to re-create it in your own page!
  * Hint: Use View Source or F12 Developer Tools in your web browser to see their HTML and CSS

## How does this actually work?

* GitHub Actions allows you to run code on GitHub's servers when something happens in your repository
  * The most common "something" is when a commit is pushed to the GitHub repository
  * Developers use this to, e.g., automatically run a test suite against new code to make sure the new code doesn't break anything
* When you configure GitHub Pages, GitHub creates a GitHub Action that builds and deploys your web page when you push new commits
  * You can see this GitHub Action by going to your repo on GitHub and clicking Actions -> pages-build-deployment
  * Clicking one of the runs will show you the three steps in this Action
  * It's not so important what these steps are. GitHub takes care of building everything and deploying the web server for you
