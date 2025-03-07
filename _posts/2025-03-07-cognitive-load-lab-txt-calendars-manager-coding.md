---
layout: post
title: "Cognitive load, lab, txt calendars, and coding managers"
---

## Cognitive load is all that matters

This is an argument that the cognitive load for a new developer to interface with your software project should be the guiding design principle for that project. Instead of focusing on abstraction, or modularity, or anyother architectural element, only consider how easy it is to understand what is going on.

This is the latest in the list of articles I've been reading recently which make explicit the complaint that new language features shouldn't be adopted unless they're easy to understand, and there are big downsides to coding as a "smart developer" since these things increase cognitive load for others.

Article: <https://minds.md/zakirullin/cognitive>

## Lab

I've been using this for a week now and am finding it useful. It's typical in my day-to-day to write lots of single-use code. I have a directory on my computer somewhere that I write these little scripts and occasionally wipe them from my system. It's a bit of an annoying workflow. Lab solves this by letting you create, edit and run files from anywhere on your computer, then clearing them out every 7 days. You create a file with `lab <ext>` where ext is the file extension. It will open in your terminal editor of choice, and save it with a timestamp filename somewhere in your `/tmp` directory. Running `lab` with no arguments lists the files (each with an index), and `lab -r <index> <executable>` will run the file at some index with some executable. For example, `lab -r 3 python3` with effectively do `python3 /tmp/path/to/my/index3file.py`.

Repo: <https://github.com/lugenx/lab>

## Replace your calendar with a... text file?

I'm big on plain text notes, but this person is selling taking things a step further. They have established a standard for plain text calendars. The idea is to use any editor to add/edit, and standard UNIX CLI tools to search, sort and inspect entries.

Article: <https://terokarvinen.com/2021/calendar-txt/>

## Should managers write code?

This is an opinion piece by an engineering leader on whether technical managers should write code or not. It's well thought out set of ideas from the author of three related books. The gist of the article is that managers should be involved in the details, but only in certain cases should they write code themselves.

Article: <https://theengineeringmanager.substack.com/p/should-managers-still-code>

