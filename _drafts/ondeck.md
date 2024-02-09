---
layout: post
title: "my title"
---

## Scriptisto 

With this tool installed, you make scripts in compiled languages (C, Rust, whatever you want) executable by using the scriptisto shebang, `#!/usr/bin/env scriptisto`. When loaded it looks through comments near the top of the file (in the language the script is written in) to define build steps. Once built, if the script hasn't changed, that means the binary can be directly executed, speeding things up. There is a neat demo in the readme where they write a simple C file, add the necessary shebang and comments, then `chmod +x script.c && ./script.c`, which of course looks wacky.

Repo: <https://github.com/igor-petruk/scriptisto>

## CLI Guidelines

A highly opinionated set of guidelines for writing CLI programs. The introduction is worth a read at a minimum. Plus it's a beautiful website (which is kind of a must if you're about to tell people how to design a UI).

Link: <https://clig.dev>

## Precision timing

It sucks to find out you've been living in the past. Here I was, talking about setting up an NTP (Network Time Protocol) server at work recently when I come across this article talking about how NTP is the predecessor to PTP (Precision Time Protocol) which has now been improved upon with SPTP (Simplified Precision Time Protocol)! Aaah!

Link: <https://engineering.fb.com/2024/02/07/production-engineering/simple-precision-time-protocol-sptp-meta/>
