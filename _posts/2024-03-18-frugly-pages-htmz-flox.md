---
layout: post
title: "frugly, pages, htmz, and flox"
---

## Frugly design

This is fun - the author wrote an app and wanted to offer a free version as well as a paid version but wasn't willing to use ads. So they made the free version look really ugly. The article is a hilarious read and I think this is a great idea for a business model! The app is completely functional when free (there are no paid "features"), but it's just really ugly. Hilarious.

Article: <https://taylor.town/frugly>

## Pages CMS

A CMS for static sites. Take dorktips for example, how do I add a post? I clone the repo, write a new post in markdown, commit and push it. It's a Jekyll site which is build using Github's CI and published using Github Pages. It's pretty simple but maybe I want to allow other contributors, write posts from a computer where git is not installed, or write posts while I'm on the bus using my phone. Pages CMS gives you an online interface to work with. I think it's a slick and simple idea.

Repo: <https://github.com/Eventual-Inc/Daft>

## htmz

This project was created in response to the very-popular-right-now htmx project. The idea with htmz is to "load HTML onto any _element_ in the page on request". So you end up writing vanilla html, but can load it into the page on demand.

As a slight aside, I see more and more projects and NDC talks on "build for the web without Javascript", or sometimes "build for the web without Javascript frameworks". As someone who has depended on frameworks for a few projects only to have them sorta-fold (I'm talking about, GatsbyJS) and then had to rewrite the whole thing, I'm really interested in this trend. Obviously frameworks are great for a lot of things but if maintenance time has to remain approximately 0, the appeal of a framework-less site becomes very strong for me. 

Link: <https://leanrada.com/htmz/>

## Flox

Okay this is basically a package manager + virtual environments but it appears they have done a really good job of making it very-cross-platform. The idea is that you can create either a developer environment or maybe build environment for some software, and push that environment up to their hub. Then pull and activate it when necessary. For software projects I depend on Dockerfiles to do this but sometimes Docker is a lot of overhead for few dependencies. I think this is really interesting for developer environments. Whenever you're on a new machine you can just `flox pull my-environment` and you're ready to go.

Key points:

- you can nest environments, and
- the packages that are available to you are from nixpkgs, which [this article](https://flox.dev/blog/nixpkgs) points out is by far the biggest package repository available. I had no idea!

Repo: <https://github.com/flox/flox>
