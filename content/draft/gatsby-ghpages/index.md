---
title: Creating Blog with Gatsby and GitHub Pages
date: "2021-05-15"
description: "A how to guide"
---

## Create the Gatsby Site

```
sudo npm install -g gatsby-cli
```

```
gatsby new gatsby-starter-blog https://github.com/gatsbyjs/gatsby-starter-b
```


## Setting up GitHub Pages


```
git remote rm origin
git remote add origin git@github.com:dermeck/dermeck.github.io.git
```

```
git push --set-upstream origin dev
```

## Deployment

```
npm install gh-pages --save-dev
```



```
npm run deploy
```

