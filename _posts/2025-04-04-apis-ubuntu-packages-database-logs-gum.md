---
layout: post
title: "One stop API docs, speed up Ubuntu packages, put logs in a database, and gUM"
---

## The one API documentation site to rule them all

This website has plugged in the API documentation for many languages and tools, and formatted it all the same. So rather than switch from the Python docs site to the NumPy docs site to the Ansible docs site, you can access them all in one place. It has a huge number of languages and tools available.

Link: <https://devdocs.io>

## 1.9x speedup for Ubuntu packages via recompilation

This person did a short investigation into whether they could speed up the `jq` binary available via Ubuntu. They tested a number of build settings and eventually realized a large speed-up was available by swapping out the memory allocator. Mostly what's cool about this short read is the authors well documented investigation process. I learned several things about how compilers work just by following along!

Link: <https://gist.github.com/jwbee/7e8b27e298de8bbbf8abfa4c232db097>

## Put your logs in a database

The author reminds everyone that databases were invented for a reason - parsing raw data is slow and terrible. Similarly, log databases exist because it is much faster to query a database than it is to `grep` text files. As well, you can "do all kinds of other database-y stuff". To showcase their point, they compare querying a log database on an old underpowered computer vs querying a repository of text files on a new overpowered computer.

Article: <https://chronicles.mad-scientist.club/tales/grepping-logs-remains-terrible>

## Mozilla gUM

A handy tool for testing the interface between your browser and computers hardware. I use this to check whether my screen sharing and mic/video should be working when I have video calls to make (rather than starting and sitting alone in an actual call). It's a good troubleshooting tool!

Link: <https://mozilla.github.io/webrtc-landing/gum_test.html>
