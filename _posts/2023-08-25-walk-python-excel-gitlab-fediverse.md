---
layout: post
title: "walk, python meets excel, gitlab meets the fediverse"
---


## walk

This is a cd/ls replacement lets you travese your filesystem using arrow keys and fuzzy search. It includes a preview option that you can have open while traversing. You can then open a file in your favorite editor (set with the `EDITOR` environment variable).

Note there is [currently a bug where if installed via snap the open-in-editor feature doesn't work](https://github.com/antonmedv/walk/issues/68).

It also doesn't elegantly handle opening a directory where the user doesn't have permission to read the contents. I had an error get thrown but I imagine this relatively young project will push support for this soon.

Overall I see this as a replacement for cd/ls _in the scenario_ where you're looking through files. I don't think I would naturally use it when I was strictly cd/ls-ing to a single known file or directory, but if I was cd/ls-ing through a bunch of files which I was inspecting, I can see using this with the preview enabled.

Repo: <https://github.com/antonmedv/walk>

## Python in Excel

Microsoft is bringing Python into Excel. There are always a lot of haters out there when it comes to Excel, but I think this will help people dip their toes in the world of software development. At some of my previous jobs I had to use Excel a lot and while I'm really glad I don't have to anymore, I think this would have been a great way to get started programming without angering my corporate overlords.

Link: <https://techcommunity.microsoft.com/t5/microsoft-365-blog/introducing-python-in-excel-the-best-of-both-worlds-for-data/ba-p/3905482>

Video: <https://www.youtube.com/watch?v=8ofsE7xiGho>

## Gitlab embraces the Fediverse

Okay I know this is two "company meets open source" stories in a row but I think this is a really cool development. Gitlab is going to start supporting the ActivityPub protocol (on which Mastodon, Bluesky, Lemmy and Pixelfed are based) in a few different ways. If you search the issues at their [core repo](https://gitlab.com/gitlab-org/gitlab/-/issues) you can see a number of relevant issues and discussions. The one I'm specifically linking to below is about leveraging the protocol for _cross-server_ merge requests. To summarize the idea:

1. You have an account on `gitlab.myserver.ca`.
2. You fork a project hosted on `gitlab.com` _using your account from `gitlab.myserver.ca`_.
3. You make edits and make a merge request from your fork to the original project.

If you imagine this being implemented on other git hosts like Github, it would allow you to self-host a git account and still contribute to projects hosted on other servers. I'm excited to see where it goes.

Link: <https://gitlab.com/gitlab-org/gitlab/-/issues/421930>
