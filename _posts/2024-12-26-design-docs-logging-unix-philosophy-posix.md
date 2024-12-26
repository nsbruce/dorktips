---
layout: post
title: "Design docs, logging defaults, unix philosophy, and POSIX time"
---

## Design docs < throwaway code

Design docs make for bad documentation because they get outdated so quickly. They also claim to answer questions that can't actually be answered before code is written. However they can be used to solicit early feedback on ideas and write down long-term focuses.

These are some of the pros and cons that the author gives for design documents which they then contrast with using draft pull requests to organize ideas and solicit feedback.

Article: <https://softwaredoug.com/blog/2024/12/14/throwaway-prs-not-design-docs>

## Sensible logging defaults

This article lists the good and the bad traits for logging. It's specifically about cloud native applications, but I think the majority are valid for non-cloud apps. I think that cloud native is the most difficult logging scenario, where you're expecting (possibly many) users to be emitting logs to some central node, and you obviously have to deal with "the" network. Applying cloud native logging practices to all logging situations will only help.

My favourite listed trait is the unix philosophies "Rule of Silence":

> When a program has nothing surprising to say, it should say nothing

Article: <https://gerlacdt.github.io/blog/posts/logging>

## unix philosophy

A follow on from the last entry on sensible logging, here is the unix philosophy captured in 17 rules. I've read variants of this list many times, but it's good to remind yourself of the ones which are your "natural weaknesses". One that I find slippery is the "Rule of Clarity":

> Clarity is better than cleverness

In my experience programmers (myself included) love to be smart while writing code. This "rule" says that we should write programs for the humans that will read and maintain them, not for the computer that injests their output or runs them.

Article: <http://www.catb.org/esr/writings/taoup/html/ch01s06.html>

## Seconds Since the Epoch

A reminder that `now.time() - before.time()` does not necessarily represent the duration in seconds between `now` and `before` if you mean seconds on a clock, and `time()` returns seconds since the epoch. Seconds since the epoch is defined using exactly 86,400 seconds per day, and ignores leap seconds. When the author wrote this article, UTC time was 29 seconds away from POSIX time.

I love reading software documentation on these things because you can tell there was a lot of thought put into any decent implementations for time management libraries. My favourite quote that the author pulls from IEEE 1003.1 is 

> Most systems' notion of "time" is that of a continuously-increasing value, so this value should increase even during leap seconds.

Article: <https://aphyr.com/posts/378-seconds-since-the-epoch>
