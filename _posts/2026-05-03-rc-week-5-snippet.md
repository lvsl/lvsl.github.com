---
layout: post
title: "[RC] Week #5: Taking time to deliberate on my coding project"
published: true
date: 2026-05-03 09:00:00
tags:
  - rc
  - coding-retreat
  - snippets
---

## Context about what "Recursers" do day-to-day
See my [Week #2 snippet]({% link _posts/2026-04-08-rc-week-2-snippet.md %}) for details.
Here's a [LinkedIn short video](https://www.linkedin.com/posts/nicholasbs_15-years-in-and-theres-still-no-place-else-ugcPost-7450566979393933312-9NzQ) where Nicholas (RC CEO) explains it really clearly.

## Week 5 Progress
My initial plan for learning Zig was to write a calculator app that supports arbitrary-precision arithmetic. The starting point was this [article about the Android calculator app](https://asteriskmag.substack.com/p/the-impossible-calculator). The goal was to re-implement the calculator written by [Hans Boehm](https://www.hboehm.info/new_crcalc/) in Zig.
That led me on a trail all the way to the *Principia Mathematica* book. I've added a list of links to papers [below](#calculator-links).

After a few weeks of digging into papers, I realized I needed a more tangible target, which pointed me toward the origins of UNIX. UNIX has two calculator tools—[`bc`](https://en.wikipedia.org/wiki/Bc_(programming_language)) and its predecessor, [`dc`](https://en.wikipedia.org/wiki/Dc_(computer_program)). Both are gems of UNIX history:
> _dc is the oldest surviving Unix language program._

The `dc` calculator has the key feature I'm looking to learn: **how to do arbitrary-precision math from scratch**.

There are two implementations derived from BSD that I'm currently aware of (GNU has its own, but I don't have a good source reference for it):
* OpenBSD by [Otto Moerbeek](https://www.drijf.net/) — [CVS repo for dc](https://cvsweb.openbsd.org/src/usr.bin/dc?sort=File) 
* MacOS by [Gavin D. Howard](https://gavinhoward.com/) — [GitHub repo for both bc and dc](https://github.com/gavinhoward/bc)

Aside from deliberating on my coding project, I'm happy that I've started talking more to folks at RC. I really enjoyed the ["Volition" workshop](https://www.recurse.com/self-directives#volitional-muscles). I had never encountered that word, "volition," before; honestly, in my 20+ years of speaking and reading the English language, it never came up, or at least I don't recall it.

## Challenges
I was reminded again that immigration is hard -- specifically, how certain tasks are actually multi-step projects with circular dependencies and blockers.


## It's ~~turtles~~ calculators all the way down :abacus: {#calculator-links}
A trail of research papers (links point to PDFs) I followed :rabbit: :arrow_right: :hole: :
* 2020: [Towards an API for the Real Numbers](https://dl.acm.org/doi/pdf/10.1145/3385412.3386037)
* 1986: [Exact Real Arithmetic: A Case Study in Higher Order Programming](https://wiki.fricas.org/public/refs/exact-real-p162-boehm.pdf)
* 1946: [Preliminary Discussion of the Logical Design of an Electronic Computing Instrument](https://www.cs.princeton.edu/courses/archive/fall13/cos375/Burks.pdf)
* 1945: [First Draft of a Report on the EDVAC](https://web.mit.edu/sts.035/www/PDFs/edvac.pdf)
* 1943: [A logical calculus of the ideas immanent in nervous activity](https://www.cs.cmu.edu/~epxing/Class/10715/reading/McCulloch.and.Pitts.pdf)
* 1925: [Principia Mathematica](https://www.uhu.es/francisco.moreno/gii_mac/docs/Principia_Mathematica_vol1.pdf)
