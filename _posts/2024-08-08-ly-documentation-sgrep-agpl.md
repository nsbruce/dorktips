---
layout: post
title: "Ly, documentation isn't communication, sgrep, and AGPL"
---

## Ly 

This is a simple TUI display manager. Works with a bunch of desktop environments (both X and Wayland). I don't use a display manager and just launch my window manager manually after startup but was tempted by the pretty TUI in this case. In other news, I always thought TUI meant "terminal user interface" because I'm a dufus but it's actually "textual user interface".

Repo: <https://github.com/fairyglade/ly>

## To document or not to document

This article from the author of Javadoc for JUnit talks about his stance that, respective to software, documentation is not as important as communication and the two are not synonymous. A good quote from the article:

> the superior programmer exercises superior design skills to avoid having to exercise superior communication skills

The gist of the article is that self-documenting code isn't the answer, and neither is writing a ton of documentation if that documentation is for unstable software, read by only a few, or done at the cost of other more beneficial work. Emphasis is placed on simplifying code such that less documentation is needed, writing tests, and using a whiteboard to communicate with other developers.

Article: <https://tidyfirst.substack.com/p/the-documentation-tradeoff>

## sgrep

A semantic grep tool which supports various models (with Google's Word2Vec being the default). It can be used just like `grep`, by piping in any text input. Unfortunately, there is another project out there named `sgrep`, which they use to mean "sorted grep".

Repo: <https://github.com/arunsupe/semantic-grep>

## AGPL

This is a license I wasn't really aware of until checking out a friends project that usesit. Since then I read this short and informative article from ParadeDB about why they use the AGPL license and directly compares it with Apache 2.0, BSL, and ELv2.

Article: <https://blog.paradedb.com/pages/agpl>
