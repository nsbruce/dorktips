---
layout: post
title: "jnv, difftastic, Radicle and ludic"
---

## jnv

This is cool! I've [written before](./2023-12-11-jq-jaq-cd-bad-graphs.md) about `jq` and `jaq` which are CLI tools for parsing JSON files. Well `jnv` takes a different approach - it's still a CLI tool but it drops you into a type of shell where you can interact with the JSON file in real-time using `jq` syntax. It's really neat and pretty much immediately replaced `jq` for me. I find that the fiddle-y part of `jq` is getting the syntax correct and `jnv` helps by letting you see the results of your queries in real-time as you type.

Repo: <https://github.com/ynqa/jnv>

## difftastic

I've always had a hard time parsing the output of `diff` and `git diff`. To be fair to them, I haven't taken the time to learn the `@@ -12,7 +12,6 @@`-esque syntax, and to be fair to me, that seems like a highly unintuitive syntax. For complicated diffs I end up using the stock VSCode diff viewer. Difftastic seems like an improvement on even that - it uses treesitter to get a syntactic diff!

Lets do a comparison. First here's the output of vanilla git diff for a [small pull request](https://github.com/TorchDSP/torchsig/pull/231) I made to a public repo recently.

![git diff](/assets/next-git-diff.png)

While here is the output from difftastic (with inline mode enabled).

![difftastic](/assets/next-git-difft.png)

I particularly like the way line numbers are shown both before and after the change. The bigger ticket item is that "gone are the days" of hunting for which character changed in a line. If a single variable changes, it's much more clearly highlighted in the diff.

The actual CLI command is `difft`, not `difftastic` (luckily).

Link: <https://difftastic.wilfred.me.uk/>

## Radicle

Decentralized Git! Radicle calls itself a "peer-to-peer collaboration stack build on Git". That means it includes the concepts of issues and pull requests overlaying the code storage which uses Git. Instead of pushing code to a central Github/Gitlab server, you push it to a network of nodes. If your Gitlab/Github server goes down you're hooped while with Radicle some number of nodes can go down and you won't be affected. They have a great FAQ page if you're interested in the mechanics of how they pull this off. I'm a huge fan of decentralization so I hope this takes off!

Link: <https://radicle.xyz>

## ludic

Are you tired of seeing React developers brag about component-based web development and having loads of fun and you can't participate because all you know is Python? Fear not! There is now a Python framework for component-based web development. Joking aside, for simple sites this may be a reasonable approach. It seems to be bred from the cult of Javascript-haters, but they are closely following the reactive architecture which has become so popular in the Javascript web/native frameworks.

Repo: <https://github.com/paveldedik/ludic>