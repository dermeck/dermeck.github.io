---
title: Creating Blog with Gatsby and GitHub Pages
date: "2021-05-20"
description: "A how to guide"
---

In this article I will describe how this blog was created based on the official starter `gatsby-starter-blog`.

## Create the Gatsby Site
Avoid installing `gatsby-cli` globally since you might run into permission errors and be tempted to install it with `sudo` to work properly. That is a bad idea. You never know which insecure dependency might be deep down in that `/node_modules` folder.

Instead use `npx` ([Node.js Package Runner](https://nodejs.dev/learn/the-npx-nodejs-package-runner)), a tool to run `npm` package binaries. The nice thing about `npx` is:
- it will let you run packages from your local `/node_mudules` folder without the need to specify the exact binary path
- if it can't find the package it will download and run it automatically

Initialize the boilerplate with:
```bash
npx gatsby new gatsby-starter-blog https://github.com/gatsbyjs/gatsby-starter-b
```

This will bootstrap the site for us. It will likely also greet as with some warnings on vulnerabilities which we will take care of next.

## Update Dependencies

We will be using `yarn` so we can delete the `package-lock.json` file.

Next we install the packages with yarn which creates the `yarn.lock` file.

```bash
yarn
``` 

To upgrade all packages to the latest version run:
```bash
yarn upgrade-interactive --latest 
```

Check all packages and proceed with enter.

## Tweaking the Site

With that all done we can look at our blog with:
```bash
yarn develop
```

This will spin up a local webserver and enable us to view the site at `localhost:8000`.

Now some tweaking can be done.  Meta data in `gatsby-config.js`, styles in `/src/styles.css` or tweaking the template for blog posts in `/template/blog-posts.js` and so on. The content can be adjusted in the `/content` folder. 

I am not going into much detail here. We have a basic working site now and can customize it however we want. 

For me the minimal layout was sufficient and I did not add any functionality yet.

## Setting up GitHub Pages

Now that we have a working site it is time to host it somewhere.

- Create Repo
- replace origin of local repo

```
git remote rm origin
git remote add origin git@github.com:dermeck/dermeck.github.io.git
```

```
git push --set-upstream origin dev
```

## Deployment

```
yarn add gh-pages --save-dev
```



```
yarn deploy
```

