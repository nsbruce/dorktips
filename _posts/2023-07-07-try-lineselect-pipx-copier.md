---
layout: post
title: "try, lineselect, pipx, and copier"
---

I'm really excited about some of the tools in this issue. Enjoy!

## try

This lets you prefix any command line operation with `try` and it sandboxes it so you can observe what will happen without actually doing it. It's essentially a dry-run for any command. Once the sandboxed command is finished running, you can choose to "commit" (actually do) the command outside the sandbox.

Repo: <https://github.com/binpash/try>

## LineSelect

If you're familiar with piping and xargs this adds an element of interactivity which I am a fan of. Essentially you pipe a command into `lineselect` and it will print out the output of the command and wait for you to select which lines you want forwarded onto the _next_ command. Their readme is really good and includes a video showcase but the minimal example is listing files, selecting which ones to delete, and then deleting them:

```bash
ls | lineselect | xargs rm
```

So `ls` runs and has it's normal output except that you can select which lines you want piped to `rm`. To enable this it seems to ensure stdout is always in single column mode. I'm not sure how it does this but it's pretty cool.

[I've offered to package this](https://github.com/chfritz/lineselect/issues/6) for the developer so it can be installed without the end user needing to install node.

Repo: <https://github.com/chfritz/lineselect>

## pipx

Installs isolated python applications. In the readme they draw the comparison between themselves and other package managers like apt. Another quote from their readme:

> In a way, \[pipx\] turns Python Package Index (PyPI) into a big app store for Python applications.

I have seen a number of recent cli tools being distributed this way. I have a good example of this just [below](#copier)...

Repo: <https://github.com/pypa/pipx>

## Copier

This is a slick tool for rendering project templates. I've been wanting something like this for quickly spinning up new projects. I've always disliked the workflow where you clone a "template" repository which is actually just a collection of files then have to go through and rename a bunch of stuff. Doing this means you inherit the git history (annoying) and the alternative is to clone the repo, delete the `.git` folder, and then re-initialize the repo. This is a pain as well.

Copier is available as a CLI app via [pipx](#pipx) (`pipx install copier`) and you can then spin up a new project with `copier copy <my-template> my/new-project`. Two neat things here:

1. the template can be a git url. No more local copy of a template necessary!
2. you can update a project to the latest version of the template with `copier update`. This is a really nice feature. Say you have a bunch of python projects and you change the CI in the template you no longer have to go manually change it everywhere.

Repo: <https://github.com/copier-org/copier>
