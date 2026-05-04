---
layout: post
title: "[RC] Week #5: Taking time to deliberate on a project"
published: true
date: 2026-05-03 09:00:00
tags:
  - rc
  - coding-retreat
  - snippets
---

## Context about what "Recursers" do day-to-day
See my [Week #2 snippet]({% link _posts/2026-04-08-rc-week-2-snippet.md %}) for details.
Here's a [LinkedIn Short video](https://www.linkedin.com/posts/nicholasbs_15-years-in-and-theres-still-no-place-else-ugcPost-7450566979393933312-9NzQ), where Nicholas (RC CEO) explains it really clearly.

## Week 5 Progress
My original plan for project - "Zig Calculator" was to follow the breadcrumbs from [article about Android calculator app](https://asteriskmag.substack.com/p/the-impossible-calculator) to re-implement calculator written by [Hans Boehm](https://www.hboehm.info/new_crcalc/) in Zig.
That lead me on a trail all the way to "Principia Mathematica" book. See details in the section below.

After few weeks of diggin into papers. I relaized I need more tangible target, which pointed me to
the origins of UNIX - the [`bc`](https://en.wikipedia.org/wiki/Bc_(programming_language)) and it's predecessor - "DC - which is great piece of
[UNIX History](https://en.wikipedia.org/wiki/Dc_(computer_program)):
> _DC - An Interactive Desk Calculator_
> _dc is the oldest surviving Unix language program._

The `dc` calculator has the key feature, I'm looking to learn - **how to do arbitrary precision math from scratch**.

Two implementations are currently I'm aware of:
* OpenBSD by [Otto Moerbeek](https://www.drijf.net/) -- [CVS repo for dc](https://cvsweb.openbsd.org/src/usr.bin/dc?sort=File) 
* MacOS by [Gavin D. Howard](https://gavinhoward.com/) -- [GitHub repo for both bc and dc](https://github.com/gavinhoward/bc)

Outside of that, I'm happy that I started to talk more to folks at RC. I relly enjoyed the
"Volition" workshop. I never encounred that word before ["volition"](https://cryptocode.github.io/blog/docs/prefix-calculator/), honestly in my 20+ years of
speaking/reading English language it never came up, or at least I don't recall that.

## Challenges
I got reminded again that immigration is hard. In one aspect - how ceraint tasks are actually
multi-step-projects-with-circular-dependencies-and-blockers.


## It's ~~turtles~~ calculators all the way down :abacus:
A trail of research papers I followed :rabbit: :arrow_right: :hole: :
* 2020: [Towards an API for the Real Numbers]()
* 1986: [Exact Real Arithmetic: A Case Study in Higher Order Programming]()
* 1961: [Signed-Digit Number Representations for Fast Parallel Arithmetic]()
* 1946: [Preliminary Discussion of the Logical Design of an Electronic Computing Instrument]()
* 1945: [First Draft of a Report on the EDVAC]()
* 1943: [A logical calculus of the ideas immanent in nervous activity]()
* 1925: [Principia Mathematica]()
