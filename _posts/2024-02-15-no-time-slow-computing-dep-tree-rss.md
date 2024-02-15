---
layout: post
title: "avoid time, slow computing, dep-tree, and RSS"
---

## Avoid programming anything to do with time

One of the first pieces of advice (related to software development) I read online was that if you're asked to write a calendar or scheduling tool, or anything in that vein, to quit your job immediately and run screaming in the other direction. I've since read a number of articles talking about the many edge-cases that appear when dealing with times and dates in software and this one is quite a good one. It lists 34 misconceptions that the author had about timezones. My personal favourite punchlines (not misconceptions) are:

1. there are more timezones than countries, and
2. Amsterdam was once offset from UTC by 19 minutes and 32.13 seconds.

Article: <https://www.zainrizvi.io/blog/falsehoods-programmers-believe-about-time-zones/>

## An argument for "Slow computing"

Similar to "slow fashion" and "slow food", this author argues that "slow computing" has a place in our world. Specifically where security and safety are concerned. The argument is framed around adding friction to our digital systems which is antithesis to the trend since forever(?) of making our digital experiences as frictionless and fast as possible.

Article: <https://www.theregister.com/2024/02/14/friction_is_good/>

## dep-tree

In a recent post I linked to an online tool that you could use to get a security snapshot of your project dependencies. Well this tool visualizes a dependency tree as a 3D interactive force-directed graph. The idea is that projects with clean dependency trees (minimal cross-over between different modules and apps) will appear as separate point clouds while closely coupled dependencies will gravitate together. I think this applies more for monorepos and larger projects than small independent repos but it's very interesting. Below is a plot from one of the repos at my work. As you can see, while there are some separated clouds they are tied together in some places.

![dep-tree example plot](/assets/2024-02-15-dep-tree.png)

They offer a tool you can run yourself and they also have a cloud offering where you paste a link to a github project and they plot it online for you.

Repo: <https://github.com/gabotechs/dep-tree>

## RSS

Old tech, still awesome. That's the gist of this article. I've been interested in RSS feeds for a while but haven't actually used an aggregator. Do you maintain an RSS feed? I'd be interested to hear. I know at least one friend that does.. shout out to Brave Dave in Kelowna. I know he uses one because he has dorktips in his feed! That's right, you can subscribe to dorktips by checking out the root [atom.xml]({{ site.url }}{{ site.baseurl }}/atom.xml).

Article: <https://www.pcloadletter.dev/blog/rss/>