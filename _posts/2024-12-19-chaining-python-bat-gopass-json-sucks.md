---
layout: post
title: "Chaining Python, bat, gopass, and JSON sucks"
---

## Python chained expressions

This quick write up discusses an interview question that a candidate got _right_ but the interviewer thought was wrong. It's not uncommon in Python to assign variables like `x = y = 5`, and check multiple conditions at once like `if x == y == z:`. In the condition check, imagine `x`, `y` and `z` are strings. It is reasonable to think that this expression would first evaluate `x == y` and get a bool (say `True`), then evaluate `True == z` which will be `False`. So no matter the values of your three variables, the result is always `False`. However, in Python chained expressions are transformed and the condition becomes `if (x == y) and (y == z):`.

Article: <https://www.ashu1461.com/interview-gone-wrong/>

## bat

From the project README: "A `cat` clone with syntax highlighting and Git integration". I call `cat` many times per day and I've just aliased `cat=bat`. It seems to work in the exact same way but with syntax highlighting for a bunch of languages, shows line numbers, and indicates changes if it's a `git` managed file. The only use case I regularly have that this screws up is `cat`-ing something then copying out a section of the file. I can get rid of the line numbers and such by doing `cat --style plain <myfile>` and I'll see if this gets annoying.

**Update:** It's been a few weeks and I'm enjoying it. It does make regular `cat` seem more bland. Syntax highlighting is nice!

Repo: <https://github.com/sharkdp/bat>

## gopass

I have been using Keepass (and the keepassxc client) to manage my passwords for more than a decade. At work we needed to have a shared password manager and a coworker did some research on the options, eventually settling us on gopass. I'm now switching all of my personal password management to gopass too, since it's just better for me. It's got a great CLI, the passwords are all stored as separate encrypted files in a basic directory structure, and authentication is offloaded to `gpg`. It's by default git managed, and if you set up a remote for the repo, it will automatically push/pull after you make changes. The thing I really like is that it's simple and easy to understand! It's pretty developer focused though - getting it setup does require an understanding of things like git and gpg. I would not call it "friendly" for the general public.

Repo: <https://github.com/gopasspw/gopass>

## Nobody Gets Fired for Picking JSON, but Maybe They Should?

Even if this article was bad (it's great) it would probably make it onto dorktips purely thanks to the article title. I have written about several JSON alternatives in previous dorktips articles, but never about ProtoBuf. This article steps through a number of the biggest JSON issues, most of which stem from too vague a specification. This means that each parser/tool has to make decisions which often don't agree. One particularly egregious example that stood out to me is that Python will serve invalid JSON (per RFC8259) for non-finite values. Wacky.

Article: <https://mcyoung.xyz/2024/12/10/json-sucks>
