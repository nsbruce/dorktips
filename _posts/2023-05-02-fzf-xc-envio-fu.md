---
layout: post
title: "fzf, xc, envio, and commandlinefu"
---

## fzf

Game changer. I've just started using it and it's immediately changed (for the better) my workflow. It's a CLI tool that stands for fuzzy find. The three main ways I use it are:

1. `Ctrl-R` (the default keybinding is overwritten but can be used in much the same way): instead of having to get an exact match and only seeing one option, get a list of fuzzy matches
2. `Alt-C`: cd into a fuzzy searched directory
3. `**<TAB>`: fuzzy autocomplete. For example `cat **<TAB>` will give you a list of fuzzy matches to cat while `code **<TAB>` will give you a list of fuzzy directories to open in your IDE.

It also has a command `fzf` which opens the fuzzy finder. I have used it as drop-in to find paths for more specific commands like `find`.

Overall I'm not going to do a better job at describing it than Andrew Quinn (<https://andrew-quinn.me/fzf>) (although I just installed with apt like the repo suggests).

Repo: <https://github.com/junegunn/fzf>

## envio

I have not used this yet since most of my development work right now is not very environment variable dependent. However, in the past I have had to war regularly with environment variables and this looks like a great tool to help with that. It's a CLI tool that helps you manage environment variables. It's written in Rust and has a nice CLI interface. It's also cross-platform. Essentially you can create encrypted environment profiles then switch between them. If you know, you know.

Repo: <https://github.com/humblepenguinn/envio>

## Command Line Fu

Kinda cute. You know when you're co-hacking with someone and they do something magical in one line? They knew some unix command you never took the time to figure out! Well, this website tries to crowd-source useful commands. Some are really "beginner" (the top voted of all time is `!!` to repeat the last command...) but some are fun!

Link: <https://www.commandlinefu.com>

## xc

This is a markdown based task runner. I've begun using it and so far it's a winner. The installation is simple (put binary in path), and then your tasks all go into a `## Tasks` section if your `README.md`. This is probably best described by example: lets ray you want to have a build task for your cpp project.

In one architecture you write a makefile then document what it's doing in your readme under some kind of "getting started" heading. In another architecture you add tasks to a task runner like "poe the poet" for python or "npm" for node and in your readme you say "install this taskrunner then use it to run my build task". If the build task is updated it has to be done in two places and you may be requiring the user to install additional dependencies just to run a build task. It's also bad design to ask users to type `sudo domybuildtask`. Developers will have to take the time to go read exactly what it's doing and decide if they trust it.

In this architecture you just add a task to your readme. Let's see a simplified example I'm currently using for a cpp project. In my `README.md` I have:

```markdown
## Tasks

This repository is [xc](https://xcfile.dev) compliant.  The following tasks are available:

### build

```bash
mkdir -p build
cd build
cmake -DCMAKE_INSTALL_PREFIX=/usr/local -DCMAKE_BUILD_TYPE=Release ..
cmake --build . --target install --config Release -j $(nproc)
```

If someone has xc in their path they can just run `xc build` and it will execute the task. If someone does not have xc, they have a clear step-by-step guide to follow.

It also lets you do things like pass arguments and use environment variables.

Repo: <https://github.com/joerdav/xc>
