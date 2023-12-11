---
layout: post
title: "jq, jaq, cd ., bad plots"
---

I've fallen behind and not just in terms of timeline - I have a lot of tabs open with dorktips fodder so I will hopefully publish a few of these articles over the next short period.

## jq 

`jq` is a CLI JSON processor. I assume it stands for "JSON query".

The simplest thing it does is pretty-print a JSON structure

```bash
~ ❯ echo '{"ugly":63,"doodad":[{"nested":"thing"}]}' | jq '.'                                                           

  "ugly": 63
  "doodad": 
    {
      "nested": "thing"
    }
  ]
}
```

We can also parse the JSON in various ways

```bash
~ ❯ echo '{"ugly":63,"doodad":[{"nested":"thing"}]}' | jq '.ugly'
63
~ ❯ echo '{"ugly":63,"doodad":[{"nested":"thing"}]}' | jq '.doodad[0].nested'
"thing"
```

If you want to try it before you buy it (jk it's FOSS, albeit with a non-standard license) out check out the [online sandbox](https://jqplay.org).

Thanks to longtime reader and avid fan, Dustin, for introducing me to this one!

Repo: <https://github.com/jqlang/jq>

## jaq

And now, in a move which I can't decide whether it's particularly stupid or a stroke of genius, I'm showing you a `jq` clone, `jaq` (said "Jaques"). It's a written in Rust and it's aim is to be a drop in replacement for `jq` but faster and with some bugs fixed.

Repo: <https://github.com/01mf02/jaq>

## `cd .`

The author of the linked blog post points out that there is a use for `cd .`. In a scenario where you have two terminals open, one is inside a directory and in the second you delete and recreate that directory. In the first you can use `cd .` to refresh the directory.

I think of the case where you're mucking around in a cmake build directory and rebuild the project including a teardown.

Article: <https://blog.meain.io/2023/navigating-around-in-shell>

## Friends don't let friends make bad graphs

This is a simple readme with a list of data visualization no-no's. The ones that stood out to me are the sample-size requirement for violin plots (I'm a recent offender) and heatmap outliers (which comes up frequently when dealing with wideband radio data in time-frequency spectrograms.

Repo: <https://github.com/cxli233/FriendsDontLetFriends>
