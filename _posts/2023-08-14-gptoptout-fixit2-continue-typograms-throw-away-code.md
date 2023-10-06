---
layout: post
title: "gptoptout, fixit2, continue, typograms, and throwing away your code"
---


## GPTBot opt-out

OpenAI now offers a method of stopping it's web crawler from using your website as training material. You can see an example of it running for dorktips here: [robots.txt]({{ site.url }}/robots.txt).

Documentation: <https://platform.openai.com/docs/gptbot>

## Fixit2

Meta has published the first(?) auto-fixing linter. It's a python linter that is heavily based on [flake8](https://flake8.pycqa.org/en/latest/) and it will automatically fix some of the issues it finds. It also let you setup custom rules and fixes which they showcase in the release announcement. There is a link to the pypi package at the end of the announcement.

Release announcement: <https://engineering.fb.com/2023/08/07/developer-tools/fixit-2-linter-meta/>

## continue

For those on the waitlist for the [VSCode Github Copilot Chat](https://docs.github.com/en/copilot/github-copilot-chat/using-github-copilot-chat) public beta. There is now an alternative. `continue` is a VSCode extension that exposes OpenAI's LLMs as an in-IDE chat window. You can access the gpt-3.5-turbo and gpt-4 models freely at first but then need to use an API key.

Repo: <https://github.com/continuedev/continue>

## Typograms

Google's hat in the ring for typographic images. [Mermaid](https://mermaid.js.org/) seems to have been taking the world by storm and while I quite like it, there are some things that are still annoying (I'm looking at you, inability-to-enforce-node-positions). As such I'm excited for some competition in this space. On the documentation what they say about Mermaid is

> Unlike libraries like mermaid, typograms are defined typographically (WYSWYG), rather than semantically (a transformation from a high level description to graphics), which picks a different trade-off: it gives you more control over the rendering (expressivity) at the cost of making you type more (productivity).

Let's try it right now. Here is what I shoved into this post:

```html
<script src="https://google.github.io/typograms/typograms.js"></script>
  <script type="text/typogram">
  +---+                        .---.
  |   |---> Welcome, dorks <--*|   |
  +---+                        '---'
</script>
```

and here is the result.

<script src="https://google.github.io/typograms/typograms.js"></script>
  <script type="text/typogram">
  +---+                        .---.
  |   |---> Welcome, dorks <--*|   |
  +---+                        '---'
</script>

Looks pretty good. It's also available as a node package.

Link: <https://google.github.io/typograms>

## Opinion: throw away the first draft of your code

This author argues that when starting a new project, it is worth the time investment for engineering teams to:

1. prototype for a few days
2. literally delete all of the code
3. actually start building the project

I won't try to summarize much further but this is a good (and short) read. Sounds scary but I am interested to try this with one of my projects soon!

Article: <https://ntietz.com/blog/throw-away-your-first-draft/>