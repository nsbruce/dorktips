---
layout: post
title: "Go lessons, SSH-Snake, csvlens, qsv"
---

## Lessons from 14 years of Go

This is a script from a talk given by Rob Pike (one of the creators of Go Lang) where he discusses lessons learned during the Go lifetime. He focuses at one point on the transition from Go being a closed source project at Google to completely open-sourced and community driven and some of the lessons learned. Overall I found it a fun read and gave interesting insight into the process of creating a language.

Article: <https://commandcenter.blogspot.com/2024/01/what-we-got-right-what-we-got-wrong.html>

## SSH-Snake

A self-replicating program designed to map a network by running through the following steps (copied directly from their readme):

1. On the current system, find any SSH private keys,
2. On the current system, find any hosts or destinations (user@host) that the private keys may be accepted,
3. Attempt to SSH into all of the destinations using all of the private keys discovered,
4. If a destination is successfully connected to, repeats steps #1 - #4 on the connected-to system.

Spooky! The purpose is to demonstrate how vulnerable a network might be to a single compromised machine.

Repo: <https://github.com/MegaManSec/SSH-Snake>

## csvlens

A command line CSV viewer. It opens a CSV file and using a TUI lets you scroll around, search, filter, etc.

Repo: <https://github.com/YS-L/csvlens>

## qsv

Said "quicksilver" this is a CSV viewer like csvlens but also offers editing and joining CSVs. It even has methods for getting a GPT model to describe the data. It is a much heavier lifter than csvlens and of course that comes with added complexity (for the user).

Repo: <https://github.com/jqnatividad/qsv>