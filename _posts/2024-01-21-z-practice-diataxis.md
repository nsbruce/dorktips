---
layout: post
title: "z, practicing, and diátaxis"
---

## z

This tool learns your most "frecent" directories. From their README:

> Frecency is a portmanteau of 'recent' and 'frequency'. It is a weighted rank  that depends on how often and how recently something occurred. As far as I know, Mozilla came up with the term.

Once trained, the shell command `z` lets you `cd` to a "frecent" directory based on regex. To demo this, I installed it (by simply adding the repos `z.sh` file path to my `.zshrc`), then created a few directories with similar paths, `cd`'d between one of them, then checked that the regex only grabbed one:

```bash
/workspaces $ mkdir -p very_used/foo/bar
/workspaces $ mkdir -p never_used/foo/bar
/workspaces $ cd very_used/foo/bar
/workspaces/very_used/foo/bar $ cd -
/workspaces $ z bar foo  # nothing happens here since this regex doesn't match anything
/workspaces $ z foo bar  # great success, running this takes us to the correct directory
/workspaces/very_used/foo/bar $ z -l  # list the "known" directories
common:    /workspaces
89784      /workspaces/very_used/foo/bar
209463     /workspaces
```

Cool! The repo README goes into some detail about how it works, but the gist is that recent directories get higher weights quickly to overcome old but frequently visited directories.

Repo: <https://github.com/rupa/z>

## Practice programming

The author argues that like playing music, or anything else you want to "be good at" (which can either mean maintaining your personal status quo, or improving), you need to practice that skill. Two quotes I liked:

> [Musicians] have to continue spending considerable amounts of time simply to maintain technique, let alone expand it.

> ... many programmers implicitly finish the bulk of their learning early on, and some stop learning entirely...

The author talks about his own experience practicing programming by automating tasks and taking on small, real world projects.

I suppose this is one of the reasons I started dorktips. I enjoy trying to keep up to date on the software world, and this article resonated with me.

Article: <https://tratt.net/laurie/blog/2022/practising_programming.html>

## diátaxis

This is a methodology for documentation which I've seen referenced a few times with respect to software. It seems well trusted, with Ubuntu, Python, and a number of other big groups committed to forming their documentation in this way. It's an architecture which outlines what documentation should be written, how it should be written, and how to organize it. The primary principle of the "what" is that everything should fall into one of 4 categories:

1. Tutorials
2. How-to guides
3. Explanation
4. Reference

I have plenty of reading left to do on this one, and I'm excited to learn more and perhaps start applying it to my own projects and at work.

Link: <https://diataxis.fr/>