## Config Files
---
<br />

[![forthebadge](https://forthebadge.com/images/badges/open-source.svg)](https://forthebadge.com)
[![forthebadge](https://forthebadge.com/images/badges/ctrl-c-ctrl-v.svg)](https://forthebadge.com)
[![forthebadge](https://forthebadge.com/images/badges/powered-by-coffee.svg)](https://forthebadge.com)


This repository contains a bunch of configuration files used by me to Bootstrap some of my projects and tools to increase my productivity. Feel free to use any of these files to enhance your productivity too!

<br />

### iTerm2 Profiles
---

Terminal is a crucial part of a developer's daily routine. A good looking and powerful terminal shell can help you save significant amount of time and efforts, so you can focus on the thing which matters the most: *Coding*!

I am a big fan of iTerm2 and zsh which provide a whole lot of useful features as compared to the traditional terminal. You can download iTerm2 from [here](https://iterm2.com/downloads.html) and oh-my-zsh, which is a framework for zsh, from [here](https://ohmyz.sh/#install).

Once, both of the above mentioned tools have been installed on the system, open the Preferences from iTerm2 menu or by simply using the keyboard shortcut `⌘,`. Then go to the **Profiles** tab, where you can create your own profile or import a theme profile.
<img width="1013" alt="Screenshot 2021-04-14 at 7 30 48 PM" src="https://user-images.githubusercontent.com/39908472/114727856-3237c580-9d5c-11eb-99ab-28a1dc5d84a3.png">


You can find a wide range of themes created for oh-my-zsh [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes).

Here are some of the profiles which I have created over time to transform the UI of my terminal shell.

- [Sombre Forest](Sombre-Forest.json)
<img width="1225" alt="Screenshot 2021-04-14 at 6 09 34 PM" src="https://user-images.githubusercontent.com/39908472/114728182-7f1b9c00-9d5c-11eb-9df6-9dcfd35c8a22.png">


- [Frosty](Frosty.json)
<img width="1150" alt="Screenshot 2021-04-14 at 6 13 31 PM" src="https://user-images.githubusercontent.com/39908472/114728215-8773d700-9d5c-11eb-9ea1-28e5206729cb.png">


<br />

### ESLint Rules
---

[ESLint config](lintconfig.js) contains the eslint rules which I find most obvious and sensible for my projects. More rules can be found [here](https://eslint.org/docs/rules/). You can play around with them and create a list of rules which suit your needs the best.

<br />

### GitHub workflows
---

Using GitHub actions and workflows, you can automate most of the tasks which you would have to otherwise perform manually. Tasks like testing, linting, building, deploying, etc. can be automated easily with GitHub actions and workflows. [Here's](https://github.com/features/actions) the official website for same. For more info, check out the [docs](https://docs.github.com/en/actions/learn-github-actions).
<br />
For workflows to work, there's a standard pattern which you need to follow. You need to have a ```.github``` directory inside your root folder, which in turn should contain a ```workflows``` folder. All of your workflow files go inside the ```workflows``` subdirectory. Although, for labeler workflow, you need to have the ```labeler.yml``` file at the same level as your workflows directory.

```
- .github
    - labeler.yml
    - workflows
        - pull_request.yml
        - deploy_gh_pages.yml
        - test_and_list.yml
            .
            .
            .
```

Here are some of the most common workflows which I use for my JS/ReactJS projects:

- **Labeling PRs** which uses [pull_request_label.yml](pull_request_label.yml) and [labeler.yml](labeler.yml).
- **Testing and linting** which uses [test_and_lint](test_and_lint.yml). They can also be broken down into separate workflows.
- **Deploying to GH Pages** which uses [deploy_gh_pages.yml](deploy_gh_pages.yml).

Some of the workflows contain additional scripts which need to be added to ```package.json``` file.

```
...
    "test": "react-scripts test",
    "lint": "./node_modules/.bin/eslint -c lintconfig.js src/",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build"
...
```

For more info on how to deploy your application to GH Pages, checkout these blogs by [Ibrahim](https://dev.to/yuribenjamin/how-to-deploy-react-app-in-github-pages-2a1f) and [Shilpi](https://medium.com/front-end-weekly/ci-cd-with-github-actions-to-deploy-on-github-pages-73e225f8f131).

<br />

---

*More config files coming soon!*
