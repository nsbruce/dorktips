---
layout: post
title: "copilot cli, inshellisense, slurp and grim"
---

In this post I have the usual, being some tools I'm trying out. I also added a small part of [my dotfiles](#slurp-and-grim) which still falls under the category of tools I'm using. Enjoy!

## Github Copilot CLI 

One of the things I _don't_ like about LLM chat bots is that they often require a context shift to interact with. You have to stop what you're doing, open a browser, do your 'chatting', then go back to the task that prompted it all. One place where the LLM interface is not as annoying is in the IDE (where it acts as autocomplete on steroids). Github Copilot is one such option and they've now moved from the IDE into the terminal.

It has two modes, `explain` and `suggest` which each take a string argument. Before replying to your prompt it asks whether this pertains to a generic shell command, a `gh` command, or a `git` command. I suppose it sends your prompt to a specifically trained model. It then either suggests or explains the command and gives you options to explain further, revise the command, rate the response, etc. 

Let's do a quick demo! I'll ask about some git rebasing since I can see this being a useful tool for un-rats-nesting git garbage fires.

```bash
~ gh copilot suggest "rebase my branch onto main and for every conflict accept main instead of my branch"

Welcome to GitHub Copilot in the CLI!
version 0.5.3-beta (2023-11-09)

I'm powered by AI, so surprises and mistakes are possible. Make sure to verify any generated code or suggestions, and share feedback so that we can learn and improve.

? What kind of command can I help you with?
> git command

Suggestion:                                                                                    
                                                                                               
  git rebase -X theirs main                                                                    

? Select an option
> Explain command

Explanation:                                                                                   
                                                                                               
  • git rebase is used to apply commits from one branch to another.                            
    • -X theirs resolves conflicts by taking the changes from the branch being rebased (main)  
    instead of the current branch.                                                             
    • main: specifies the source branch (main) and the target branch is the current branch.    
                                                                                               

? Select an option  [Use arrows to move, type to filter]
> Exit
```

That looks pretty good. Interestingly I reran the exact same thing and the suggestion was `git rebase -Xtheirs main` without a space between `-X` and `theirs`. So as the warning after the prompt indicates, YMMV. It's also evidently not searching the web because I asked it to explain `tspin -f` (from my last post) and it didn't respond. Luckily, it didn't make up garbage and instead said "try again".

```bash
~ ❯ gh copilot explain 'tspin -f'

Welcome to GitHub Copilot in the CLI!
version 0.5.3-beta (2023-11-09)

I'm powered by AI, so surprises and mistakes are possible. Make sure to verify any generated code or suggestions, and share feedback so that we can learn and improve.

Explanation not readily available. Please revise for better results.
```

This is cool work! I'm keen to try some open-sourced alternatives too, so if anyone out there has specific recommendations let me know!

Link: <https://github.com/github/gh-copilot>

## Inshellisense

Another one from the Microsoft cookbook, we have a shell autocompleter with a zinger of a name. They apparently have maked in autocomplete for 600+ CLI tools but I haven't been able to find a list of them anywhere. Instead of ML-ing this I think they just parsed man pages to extract the goodies or something similar. You start it up with `is` and then it hijacks your prompt as you type to offer autocompletions. The gif at the top of their README tells the story.

I actually haven't been able to use this yet since [there is an open issue about using handling dynamic prompt detection](https://github.com/microsoft/inshellisense/issues/120) and I use powerlevel10k as a prompt. I'll keep my eyes on it for a bit!

Repo: <https://github.com/microsoft/inshellisense>

## slurp and grim

I'm offering these two up as a special combo deal. I switched my compositor from X to Wayland recently and have had to figure out some replacements for basic utilities like screenshotting. To this end, `slurp` lets you select a region of Wayland-composed screen. When you run `slurp`, it lets you drag a rectangle on your screen then it outputs the top left coordinate of the rectangle as well as its width and height.

In this example I selected from the top left of my screen to not-quite the bottom right.

```bash
~ slurp
0,0 1920x1079
```

`grim` is a tool that makes images from a Wayland compositor. It has options to grab an entire display or a region, and whether to save to file or clipboard. The region option argument is the same shape as the `slurp` output. So I have my Print key bound to

```bash
grim -g "$(slurp)"
```

which saves my selection to my `~/Pictures` directory.

Repo (slurp): <https://github.com/emersion/slurp>
Repo (grim): <https://git.sr.ht/~emersion/grim/>
