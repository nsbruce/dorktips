---
layout: post
title: "git, jesth, and mojo"
---

## Thoughts on Github, git and Microsoft

It feels a bit like cheating to simply point you at another article, but I really think this is a great read. It took about 10 minutes for me to fully digest the authors thoughts and open about 30 embedded links.

Interesting stances that author takes:

- git isn't _that_ great. There are real alternatives that don't solve every problem git has, but solve some. If we don't give them a chance or at least consider them, we might all end up locked into a piecemeal VCS that is git. The author mentions several and what he likes about them.
- Pull Requests have become the defacto standard for a coding workflow and are premised on low-trust. This _can_ be important for large teams, open-source projects, etc. but especially on a small team (even in large organizations) a high-trust environment is required to encourage independence and autonomy. A quote the author cites from a different article by Jessica Kerr is:
    > Pull requests are an improvement on working alone. But not on working together.
- there is a piece in there on Copyright vs Copyleft licensing I had to search for on DuckDuckGo. Copilot wrote the following when prompted by the word "copyleft", and I confirm it's an exact quote from the cited page:
    > Copyleft is a general method for making a program (or other work) free (in the sense of freedom, not “zero price”), and requiring all modified and extended versions of the program to be free as well. - _[Copyleft: Pragmatic Idealism](https://www.gnu.org/copyleft/copyleft.html)_
- There is a bunch in there on Github itself being driven by profits.
- The author makes several recommendations to avoid homogenization of the developer experience. A quote he makes that resonated with me is:
    > I learn something from every new tool I use, even if it doesn’t become my new default. It makes me more resilient to change and gives me a holistic understanding what I need to develop software.

My desire for "Dork tips" is tightly related to this sentiment.

Article: <https://blog.edwardloveall.com/lets-make-sure-github-doesnt-become-the-only-option>

## Jesth

Do you regularly use TOML (nesting is hard), YAML (bespoke ambiguity), or JSON (unreadable by humans)? The readme of the repo briefly outlines the shortcomings of each before introducing JESTH (Just Extract Sections Then Hack'em).

The essence is that the document is split into TOML-like sections but the jesth parser does something like "lazy-parsing" (my phrase, not theirs). After loading in the sections, you can pick how to treat each.

They syntax looks slick too!

Repo: <https://github.com/pyrustic/jesth>

## Mojo

A company called Modular announced a superset of Python called Mojo which compiles normal python code into MLIR. The article goes into way more background but MLIR is a a replacement for LLVM's IR which is specifically designed for machine learning tasks (I know I'm not going into enough detail here but the article is really very good). The end result is that you get a C/Rust-comperable binary without needing to write anything other than vanilla Python. There _are_ a few Mojo specific annotations you can add to your code to help the compiler out, but they are optional, and really sensible. One is a struct and the other is `fn`, a replacement for the `def` keyword which requires your method is strictly type-annotated.

I do urge critics to read the article since the author does a great job explaining why Python, why not C/Julia/etc, what are LLVM and MLIR, and the benefits of deploying code using Mojo.

Link: <https://www.fast.ai/posts/2023-05-03-mojo-launch.html>
