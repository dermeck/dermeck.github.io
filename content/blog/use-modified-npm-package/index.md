---
title: "How to: use a modified version of an npm package"
date: "2022-10-14"
description: "How to use `yarn link` to develop a local version of the package and `yarn patch` to use the modified version in your project."
---

(with yarn)

## working with a local version of a package

1. change and build the consumed package locally
2. link the consumed package in the consuming project
`yarn link <local-path-to-consumed-package>`

For more advanced use cases have a look at yalc.

## use changes from local version
(... until changes are part of official package release :) )

1. Create the Patch
`yarn patch <package-name>`
you will get the terminal output: "You can now edit the following folder: /tmp/.../user"
replace `dist` and `lib` folder with the equivalents from your local package copy

2. Add the Patch
`yarn patch-commit -s /tmp/.../user` (as shown in the terminal output)

You will get a new file in your `.yarn/patches` folder and a resolutions entry in your `package.json`.
(similar to: https://github.com/dermeck/feeds-sidebar/pull/151/commits/3ae028c7d2b70ecd2c5068ff81ed6a328eb48ce1)

3. Apply the Patch
Perform an install with `yarn`

## Ressources:
- https://yarnpkg.com/cli/link
- https://yarnpkg.com/cli/unlink
- https://github.com/wclr/yalc
- https://yarnpkg.com/cli/patch
