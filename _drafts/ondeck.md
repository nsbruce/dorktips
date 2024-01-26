---
layout: post
title: "my title"
---

## Random number generator in your head

This article walks through how to generate 2 digit "pretty random" numbers quickly and in your head. The author does over the history of the method, why it works, and alternatives to it.

In a nutshell:

1. Pick a seed
2. Add the 10s digit to 6 times the 1s digit

It's a pretty math-y article but the explanations of how it works is cool. The only downside is that they explore the algorithm using demo snippets of code in a language called [Raku](https://raku.org/), which I have never heard of and had a hard time reading.

Article: <https://www.hillelwayne.com/post/randomness>

## Understanding dependencies

This website helps create a dependency tree for a given package, and checks for things like security vulnerabilities and licenses. It supports npm, go, maven, pypi, nuget and cargo, and regenerates the entire dependency structure once per day. I have been using it when reviewing merge requests. Sometimes the developer who's code I'm reviewing added some new package I've never heard of, and I'll often skim the docs to ensure the package inclusion makes sense, but this is a great tool to quickly check for what else lurks in the packages dependencies.

There is also a free API for the data that the website is serving but I haven't used it yet (and probably won't, the website is slick).

Link: <https://www.deps.dev>
