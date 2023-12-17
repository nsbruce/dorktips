---
layout: post
title: "critique, retries, pyapp and tailspin"
---

## Critique 

This article describes the internal code-review tool, Critique, used at Google. While the tool itself is interesting, it's not publically available. What interested me most about this article was the amount of time and energy that Google has put into reducing friction for this process. They have done research on tons of interesting little details like whether anonymizing the process helps (it doesn't), and how to reduce the sense of defensiveness that many people adopt when their code is criticized. There are links to some of that research in the article too.

Article: <https://read.engineerscodex.com/p/how-google-takes-the-pain-out-of>

## Retries

An article about request-retry best practices. The visualizations are really fun and informative and not the claimed 11 minutes long! The salient points are:

- don't automatically retry requests too quickly,
- exponentially increase retry delays on repeated failures,
- add jittery to the delays to prevent clients synchronizing their requests.

Article: <https://encore.dev/blog/retries>

## PyApp

This wraps a Python application into a stand-alone binary. At first I was having a hard time differentiating this and pipx (which I wrote about in a prior post) but the major difference here is that the result is executable without any surrounding infrastructure. With pipx you run the application with something like `pipx my_app_name` whereas once PyApp has been wrapped around the application you simply run `./my_app_name`. So it's a different use case. Neato.

Repo: <https://github.com/ofek/pyapp>

## tailspin

A log file colorizer (and more I imagine). You install it, then instead of the typical `tail mylog.log` or `less mylog.log` or whatever, you use `tspin mylog.log` and it parses and colors "numbers, dates, IP-addresses, UUIDs, URLs and more". It works with no config but also allows customization.

Repo: <https://github.com/bensadeh/tailspin>
