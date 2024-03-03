---
layout: post
title: "avoiding meetings, tbmk, fontimize, and oklch"
---

## Avoid meetings

This subtly titled article, "How to Keep Engineers Out of Meeting Hell," is a shorty but a goody. It's the somewhat usual list of tips for ensuring that meetings are useful to the attendees, but with a particular spin on it for engineers. Some tips for those planning or attending meetings are:

- Ask "how will we know when this meeting is over?" at the start of the meeting,
- Remember that a desired _outcome_ of the meeting is as important as having an agenda,
- Realize that if someone can attend a meeting and work on something else at the same time, then their attendance is unnecessary.

Article: <https://morethancoding.com/2024/02/16/how-to-keep-engineers-out-of-meeting-hell/>

## Tbmk

Tbmk (Terminal bookmarker) is a cli tool for managing terminal commands. The idea is exactly the same as for web browser bookmarks - you probably don't need to bookmark your corporate email login page but you will want to bookmark the page you have to visit every 9 months to change your password. Similarly, it doesn't make sense to bookmark your daily-driver commands but that weird firewall rule you have to look up every now and then slots right into Tbmk.

Repo: <https://github.com/linhx/tbmk>

## Fontimize

This is a Python package that optimizes font files for your website. You pass it a font file and either a directory or HTML file and it generates a new file which is a subset of the original font file, containing only the characters that are actually used on your site. The article is a good read on the why and how of font optimization.

Article: <https://daveon.design/introducing-fontimize-subset-fonts-to-exactly-and-only-your-websites-used-characters.html>

## OKLCH

News to me, but there's another color specification system (think RGB, Hex, HSL, etc.) called OKLCH.

- L: lightness
- C: chroma
- H: hue

There is also an "a" for opacity. The article explains the benefits of OKLCH over other specifications which seems to be mostly about perceptual uniformity, readability, and ease of palette generation.

Article: <https://evilmartians.com/chronicles/oklch-in-css-why-quit-rgb-hsl>